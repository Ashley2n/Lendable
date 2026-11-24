# How principles are enforced, and when a slice is done

Source: decision TL6 in the vault's `decisions.md`.

## Enforcement
- **Build:** `Directory.Build.props` and `.editorconfig` turn analyzer warnings into errors.
- **Tests:** `tests/Lendable.ArchitectureTests` (ArchUnitNET) checks the layer rules from `principles.md`, starting with P-ARCH-1.
- **Review:** every PR has a table of the principles it touched. Only review checks P-ARCH-2 and P-ARCH-6 (one save per use case), P-CODE and P-SOLID.

When a check fails, help her read the failure. The fix is hers to write.

## Done
A slice is done when the five checks in `plan.md` ("Definition of done", in the vault) are met. CI must be green before anything merges into `main`.
