# Release Process

This document describes the process for releasing a new version of the REFrACT **ontology** (`Ontologies/refract.ttl`), and separately, the process for **repository-only** changes that don't touch the ontology.

There are two release types:

1. **Ontology release** (`vX.Y.Z`) - used whenever `Ontologies/refract.ttl` changes, whether or not repository changes are included in the same release. Follows the major/minor/patch versioning scheme below.
2. **Repository-only release** (`vX.Y.Z.a`) - used when only repository content changes (documentation, this process document, Definitions pages, etc.), with no change to `Ontologies/refract.ttl`. `X.Y.Z` stays fixed at the current ontology version; `a` increments with each repository-only release and carries no semantic versioning meaning of its own. See [Repository-Only Releases](#repository-only-releases) below.

### Ontology Versioning Scheme

The ontology follows a major/minor/patch versioning scheme:

- **Major** (e.g. 1.1.0 → 2.0.0): breaking changes - removed or renamed classes/properties, changes to existing axioms that affect conformance.
- **Minor** (e.g. 1.0.1 → 1.1.0): additive, backward-compatible changes - new classes, new properties, new axioms.
- **Patch** (e.g. 1.0.0 → 1.0.1): non-logical changes only - annotations, comments, `rdfs:seeAlso`, documentation. No impact on axioms or entailments.

----

## Ontology Release Process

### 1. Start a release branch

Create a branch named `release/vX.Y.Z` for the target version. All changes for this release - both to `Ontologies/refract.ttl` and to any accompanying documentation - are made in this branch, isolated from `main`.

Download the raw `refract.ttl` from the newly-created `release/vX.Y.Z` branch and save it locally as `refract-X.Y.Z.ttl`. All ontology edits for this release are made in this local file, not directly in `refract.ttl`. Downloading from the branch (rather than duplicating a local working copy) avoids working from a stale version if local files have drifted from `main`.

### 2. Finalise the ontology changes

When ready for release, update the following in `refract-X.Y.Z.ttl`:

- `dcterms:modified` → today's date
- `owl:priorVersion` → the versionIRI of the previous release (e.g. `<https://w3id.org/refract/1.0.0>`)
- `owl:versionIRI` → the new versionIRI (e.g. `<https://w3id.org/refract/1.0.1>`)
- `owl:versionInfo` → the new version string (e.g. `"1.0.1"`)

Also update the **Version** field in the top-level `README.md`'s Ontology Metadata section to match.

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

### Ontology
- Revised `rdfs:comment` for `fract:CompositeAction` to clarify that a composite action
  represents a batch of changes in a single action, rather than a single logical change.
- Added `rdfs:seeAlso` annotation to every refactoring action, referencing its
  corresponding page in the REFrACT GitHub repository.

### Repository
- Added `Governance/RELEASE-PROCESS.md`, documenting the release workflow.
```

Commit `CHANGELOG.md` to the `release/vX.Y.Z` branch (not in `main`).

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

When completing the deposit form for the new version:

- **Publication Date**: use today's date (matching `dcterms:modified`) - this is the version-specific release date shown in Zenodo's version history, not the original publication date
- **Version**: add the latest release version number
- **Dates** (optional field): add a date of type "Updated" with today's date, and description "See CHANGELOG.md on GitHub"

----

## Repository-Only Releases

Used when only repository content changes - documentation, this process document, Definitions pages, etc. - with no change to `Ontologies/refract.ttl`. As nothing is being deployed to `semanticweb.tools` or Zenodo, this is a simpler release process, with no `.htaccess` change, no server upload, and no Zenodo upload.

The version number takes the form `vX.Y.Z.a`, where `X.Y.Z` is the current ontology version (unchanged) and `a` is a sequential counter starting at `1`, incrementing with each repository-only release since the last ontology release. `a` carries no SemVer meaning - it does not indicate patch/minor/major significance, only sequence.

### Process

1. Create a branch named `release/vX.Y.Z.a` for the target version (e.g. `release/v1.0.1.1`). Make the repository changes in this branch - no direct commits to `main`.
2. Add a new entry to `CHANGELOG.md` under the `### Repository` heading for the current version, describing the change.
3. Merge `release/vX.Y.Z.a` into `main` via pull request.
4. Tag the merge commit: `git tag vX.Y.Z.a` (e.g. `v1.0.1.1`).
5. Push the tag. A full GitHub Release (with notes, attached binaries) is not required, since there is no new artefact being archived - the tag alone is sufficient to mark the point in history.

When the next ontology release ships, the `.a` counter resets - the first repository-only release after `v1.1.0`, for example, begins again at `v1.1.0.1`.

----

## Notes

- `owl:versionIRI` and `owl:versionInfo` are the primary version identifiers and must always be updated together with `owl:priorVersion`.
- `dcterms:issued` is the original publication date and is never changed on subsequent releases; only `dcterms:modified` updates.
- The `.htaccess` change (step 6) must precede the file uploads (step 7), so that the unversioned path never serves new content ahead of the dedicated versioned route existing.
- When a major version ships (e.g. 2.0.0), archive the prior major version's entries from `CHANGELOG.md` into a separate file (e.g. `CHANGELOG-1.x.md`), leaving the active `CHANGELOG.md` scoped to the current major line. This keeps the active changelog from growing indefinitely.
