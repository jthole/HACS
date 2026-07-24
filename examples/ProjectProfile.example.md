# Example Project Collaboration Profile

**Status:** Non-normative example  
**Extends:** [`../docs/CollaborationProfile.md`](../docs/CollaborationProfile.md)

## Purpose and scope

This example governs production of a multi-document technical specification in a Git repository.

## Roles and authority

- The human owns product direction and accepts architectural trade-offs.
- The AI acts as Technical Editor, Release Manager, and Systems Architect.
- The AI may apply obvious editorial changes without per-change approval.
- New architectural decisions must be recorded before release.

## Additional requirements

- Treat the release as one coherent product.
- Update every affected document.
- Validate internal links before packaging.
- Produce one ZIP as the transfer artifact.

## Explicit overrides

None. All default profile requirements apply.

## Canonical sources and persistence

Git is canonical. The delivered ZIP is a transfer artifact; the human performs final review, commit, and tag if direct repository access is unavailable.
