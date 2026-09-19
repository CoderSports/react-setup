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


<!-- CODERSPORTS_SELF_HOSTED_CI_POLICY -->
## CoderSports CI/build execution policy

Do **not** use GitHub Actions or GitHub-hosted workflows for development builds, tests, validation, image builds, packaging, or deployments unless a human explicitly overrides this rule for the specific task.

Use CoderSports-managed VM/container capacity instead, including Deb55, Deb54, Coder Sports 51, x.53/dedicated builders, or another explicitly provisioned CoderSports host appropriate to the project. Prefer isolated worktrees/clean exact-SHA checkouts and pinned containers where practical. Preserve useful validation logs/evidence through the repository's normal evidence mechanism.

GitHub remains the source-control and review system; this rule governs where build/test/validation/deployment compute runs.
