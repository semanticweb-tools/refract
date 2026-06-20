# Release Process

This document describes the process for releasing a new version of REFrACT (the vocabulary, defined in `Ontologies/refract.ttl`).

REFrACT follows a patch/minor/major versioning scheme:

- **Patch** (e.g. 1.0.0 → 1.0.1): non-logical changes only - annotations, comments, `rdfs:seeAlso`, documentation. No impact on axioms or entailments.
- **Minor** (e.g. 1.0.1 → 1.1.0): additive, backward-compatible changes - new classes, new properties, new axioms.
- **Major** (e.g. 1.1.0 → 2.0.0): breaking changes - removed or renamed classes/properties, changes to existing axioms that affect conformance.

## Process

### 1. Start a release branch

Create a branch named `release/vX.Y.Z` for the target version. All changes for this release - both to `Ontologies/refract.ttl` and to any accompanying documentation - are made in this branch, isolated from `main`.

Download the raw `refract.ttl` from the newly-created `release/vX.Y.Z` branch and save it locally as `refract-X.Y.Z.ttl`. All ontology edits for this release are made in this local file, not directly in `refract.ttl`. Downloading from the branch (rather than duplicating a local working copy) avoids working from a stale version if local files have drifted from `main`.

### 2. Finalise the ontology changes

When ready for release, update the following in `refract-X.Y.Z.ttl`:

- `dcterms:modified` → today's date
- `owl:priorVersion` → the versionIRI of the previous release (e.g. `<https://w3id.org/refract/1.0.0>`)
- `owl:versionIRI` → the new versionIRI (e.g. `<https://w3id.org/refract/1.0.1>`)
- `owl:versionInfo` → the new version string (e.g. `"1.0.1"`)

### 3. Commit to GitHub

Copy the contents of the local `refract-X.Y.Z.ttl` into `Ontologies/refract.ttl` on GitHub, committing to the `release/vX.Y.Z` branch - **not** `main`.

### 4. Document the changes

Run:

```
git diff main..release/vX.Y.Z -- Ontologies/refract.ttl
git diff main..release/vX.Y.Z -- . ':!Ontologies/refract.ttl'
```

The first shows changes to the ontology itself; the second shows everything else in the release branch (documentation, Definitions pages, RefactoringActions pages, etc.), using a pathspec exclusion so it automatically covers any folder, including ones that don't exist yet.

Read through both and summarise each distinct change in plain language (not the raw diff syntax) as a new entry in the root-level `CHANGELOG.md`, e.g.:

```markdown
## [1.0.1] - 2026-06-20

### Changed
- Revised `rdfs:comment` for `fract:CompositeAction` to clarify that a composite action
  represents a batch of changes in a single action, rather than a single logical change.
- Added `rdfs:seeAlso` annotation to every refactoring action, referencing its
  corresponding page in the REFrACT GitHub repository.
```

Commit `CHANGELOG.md` to the `release/vX.Y.Z` branch (again, not `main`).

### 5. Merge, tag, and release

1. Merge `release/vX.Y.Z` into `main`.
2. Tag the merge commit: `git tag vX.Y.Z`.
3. Push the tag.
4. Create a GitHub Release for the tag:
   - Title: `vX.Y.Z`
   - Release notes: the same summary written for the `CHANGELOG.md` entry
   - Attach `refract-X.Y.Z.ttl` as a binary asset, named to match the version (not the generic `refract.ttl`), so the file is self-identifying if downloaded outside the context of the release page

### 6. Update the semanticweb.tools `.htaccess`

Add a new versioned rewrite rule, alongside the existing ones (do not remove or modify prior rules):

```apache
RewriteRule ^ont/refract/X\.Y\.Z$ /ont/refract-X.Y.Z.ttl [L]
```

This must be done **before** step 7, so the versioned path resolves correctly the moment the file is uploaded.

### 7. Deploy to semanticweb.tools

1. Upload `refract-X.Y.Z.ttl` to the server, filename unchanged. This is the permanent, frozen snapshot for this version, served at `w3id.org/refract/X.Y.Z`.
2. Rename the local copy of `refract-X.Y.Z.ttl` to `refract.ttl` and upload it, overwriting the current live file. This becomes the new "current" version, served at the unversioned `w3id.org/refract` and via the fragment rewrite rule.

Prior versioned snapshots (e.g. `refract-1.0.0.ttl`) are not touched - once published, a versioned snapshot is permanent.

### 8. Upload to Zenodo

Manually upload `refract-X.Y.Z.ttl` to the existing Zenodo deposit as a new version.

This mints a new version-specific DOI for the release (archived permanently, for anyone who needs to cite or pin this exact snapshot). The deposit's **concept DOI** (`10.5281/zenodo.20742084`) always resolves to the latest version automatically and requires no action.

`refract.ttl`'s own citation metadata (`dcterms:bibliographicCitation` and `bibo:doi`) references the **concept DOI**, not a version-specific one, and does not need to be updated on each release - it only changes if the concept DOI itself ever changes, which is not expected.

## Notes

- `owl:versionIRI` and `owl:versionInfo` are the primary version identifiers and must always be updated together with `owl:priorVersion`.
- `dcterms:issued` is the original publication date and is never changed on subsequent releases; only `dcterms:modified` updates.
- The `.htaccess` change (step 6) must precede the file uploads (step 7), so that the unversioned path never serves new content ahead of the dedicated versioned route existing.
- When a major version ships (e.g. 2.0.0), archive the prior major version's entries from `CHANGELOG.md` into a separate file (e.g. `CHANGELOG-1.x.md`), leaving the active `CHANGELOG.md` scoped to the current major line. This keeps the active changelog from growing indefinitely.
