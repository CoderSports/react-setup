# CoderSports Repository Agent Instructions

## CI and build execution

Do **not** use GitHub Actions / GitHub-hosted workflows for development builds, validation, test execution, image builds, packaging, or deployment unless a human explicitly overrides this rule for the specific task.

CoderSports has self-managed VM/container capacity available for engineering work. Prefer the appropriate CoderSports host and run required tooling in containers there when useful:

- **Deb55** — primary development / production-adjacent host for IDE Next and related services.
- **Deb54** — infrastructure/storage host with Docker/container capability.
- **Coder Sports 51** — additional CoderSports VM capacity where appropriate.
- Other explicitly provisioned CoderSports builders/VMs (for example dedicated image builders) may be used when the project requires them.

For validation:
1. Materialize an isolated worktree or clean checkout at the exact SHA.
2. Run tests/builds on an appropriate CoderSports VM, preferably in a pinned container where practical.
3. Preserve useful logs/evidence locally or in the repository's normal validation evidence mechanism.
4. Do not consume GitHub Actions minutes merely to obtain CI evidence.

GitHub remains the source-control/review system; this rule concerns **where compute-heavy CI/build/test/deploy work runs**.
