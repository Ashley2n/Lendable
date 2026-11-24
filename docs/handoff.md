# Handoff: Lendable slice 1, T1-T3 review done, T3 prediction and T4 pending

Date: 2026-11-24. Next session: finish the T3 prediction check, then start T4.

## Mode
Coach mode (`CLAUDE.md`). T3 is a 🔧 chore, so the AI may walk it through. T4 is 🧠 learning: Ashley writes every line, you edit zero `*.cs` / `*.razor` files, and you climb the hint ladder one rung per ask (`docs/coach/hint-ladder.md`). Grill-me style: one question at a time, with a recommended answer.

## Where things are
- Tickets, decisions, plan: vault `~/Documents/03-Resources/MyVault/01-Projects/Personal-Projects/Tool-Library/Docs/` (`slice-1-spec.md`, `decisions.md` TL5/TL6, `plan.md`).
- Repo: `D:\01-Projects\Personal-Projects\Lendable`, branch `main`, **no commits yet**, everything untracked. No remote checked.

## State after the T1-T3 review
- Done this session: removed duplicate `<Nullable>` from the six `.csproj` files, wrote a one-line `README.md`, thinned `CLAUDE.md` to 18 lines with details in `docs/coach/*.md`.
- Done by Ashley meanwhile: `ProjectReference`s added (Application, Infrastructure, Web), `AnalysisLevel` is now `latest-Recommended`, both `UnitTest1.cs` deleted. `dotnet test` now says "No test is available" until T4 adds one.
- Build was green (0 warnings, 0 errors) at last run.

## Open items
1. **T3 prediction check (hers to run).** Her written prediction: "unused private method throws a warning because it's stale". Gap named: `TreatWarningsAsErrors` turns warnings into errors, and `.editorconfig` never sets a severity for the unused-private-member rule, so the build may stay green. If it does, she needs a mistake that fails: `.editorconfig:82` (`dotnet_style_readonly_field = true:warning`) or a null assigned to a non-nullable `string`. Record result in the card's predictions log; a wrong prediction is a `reasoning/*` line for `02-Areas/Learning/review-log.md` (lessons only).
2. **T2 step 7.** `Counter.razor` and `Weather.razor` are still in `Lendable.Web`. Whether to delete them is her call.
3. **T4 (learning).** She answered Q1 (add a project reference from the test project to Domain). On Q2 she said she doesn't know why the mutation check exists. She gave rung 2: an empty Domain makes the rule pass without checking anything, and she should look in the ArchUnitNET README for what happens when a rule matches no types (unverified for the installed version). Xunit is 2.9.3, so use `TngTech.ArchUnitNET.xUnit` (T4 step 1). Next: her answers to the `TreatWarningsAsErrors` question and "what does green on an empty Domain tell you". Do not give code until she asks for rung 3 or 4.
4. **Vault upkeep.** T5 notes still say "this Mac" and arm64, but she is on Windows 11. `repo-claude-md.md` is out of step with the thinner repo `CLAUDE.md`. Her vault, so ask before editing.
5. **Before pushing.** Commit T1, T2, T3 as separate commits (recommendation, ⚠ unsourced). `main` isn't protected until T7.
6. Unanswered quiz from the review: which two rules stayed inline in `CLAUDE.md`, and why.

## Suggested skills
- `dev-workflow:review-me` when she wants to practise reviewing her T4 change.
- `dev-workflow:teach-back` before slice 1 closes (T9).
- `mattpocock-skills:grilling` for the card grill in T6.
- `mattpocock-skills:tdd` only as a coach for T6, never to write her code.
