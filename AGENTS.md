# Light Remote MCP — agent development instructions

## Shared engineering protocol
This repository uses the same cross-project method as the [atcelik shared AI engineering standard](https://github.com/atcelik/piyasa-info-ai-studio/blob/main/shared_control/AGENT_ENGINEERING_STANDARD.md). These local rules are sufficient even if the central document is unavailable. Upstream background: [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) (MIT); its 25 skills are **not** installed merely by mentioning them here.

1. Before editing, inspect existing code, tests, deployment rules, recent changes and the applicable branch; record an observed baseline.
2. For defects, reproduce -> localize -> isolate -> fix root cause -> add regression coverage. Do not guess, hide errors or disable checks for a green result.
3. Make minimal reversible changes, preserve existing behavior, interfaces and secrets, and avoid unrelated rewrites.
4. Run available relevant tests and builds; for UI, verify in a browser and on suitable screen sizes. Report exact evidence; if not run, state **Not tested**.
5. Review the diff for security, performance, accessibility, compatibility and rollback implications.
6. Use reviewable pull requests by default. A code change, commit or successful queue submission is not a production deployment. Do not merge, deploy, publish, send email or change live data without the applicable authorization and verification.
7. No new paid dependencies, extra polling workers or GitHub Actions jobs for this policy. Keep existing runtime and operational paths.
8. Select only relevant agent-skills workflows (context, debugging, frontend, testing, review, shipping) rather than loading all of them for every task. Existing project quality gates must not be weakened.

## Binding repository lanes and security
**READ REPO_LANES.md before any development or merge.** main is the V / Primary product authority. reviewer/openai is a downstream reviewer-specific overlay; do not accidentally merge its transport assumptions into main. Do not resurrect retired Netlify deployment.

- Respect authorization, device/session boundaries and filesystem/terminal command policies. No arbitrary elevated privileges, credential disclosure or unsafe remote execution.
- Inspect .light-remote-lane.json and existing lane/self-tests before changing adapters, deploy scripts, transport, plugin or security.
- Preserve public interfaces and client compatibility across platforms; explicitly test the affected transport and relevant cross-platform clients.
- Do not change service topology, remote device state or release production clients when only engineering-rule adoption was authorized.

## Handoff
Provide touched files, checks actually executed, regression risks, PR/commit, and status of deployment (if any). State uncertainties rather than claiming success without proof.
