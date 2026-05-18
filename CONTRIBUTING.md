# Contributing to xgoose

Thanks for thinking about contributing! xgoose is a small open-source
project, so we keep the process light. This file applies to every repo in
the **xGoose-dev** org by default — individual repos can override it with
their own `CONTRIBUTING.md`.

## Where to start

- **Use a skill or hit a bug?** Open an issue on the relevant repo. If
  you're not sure which one, [`xgoose-web`](https://github.com/xGoose-dev/xgoose-web)
  is a safe catch-all.
- **Want to publish a skill?** Skills live in their own files
  ([`xgoose-skills`](https://github.com/xGoose-dev/xgoose-skills)) and on
  the registry at [xgoose.org/skills](https://xgoose.org/skills/). See
  the [skill format docs](https://xgoose.org/docs/skills/) for the `.xgs.js`
  spec.
- **Want to add a feature to the agent?** Open a discussion or issue
  describing the use case first — the agent surface is intentionally
  small.

## Pull requests

- Keep PRs focused. One topic per PR makes review fast.
- Match the surrounding style. Most TypeScript repos run Prettier; CSS in
  the chat panel lives in `xgoose-core/packages/ui/src/panel.ts`.
- Add or update README / docs when behavior changes — every repo's README
  is rendered to xgoose.org/docs.
- For protocol changes (agent ↔ skills ↔ gateway), bump the relevant
  version constant and call it out in the PR description.

## Local development

Each repo has its own quickstart in the README. The common toolchain is:

- Node 22+
- npm workspaces (the agent core, page controller, skill runtime and UI
  are workspaces of `xgoose-core`)
- `wrangler` for the Cloudflare Worker in `xgoose-web/worker`

## Code of Conduct

By participating you agree to follow our [Code of Conduct](./CODE_OF_CONDUCT.md).
Be kind, be curious, and assume good faith.

## Security

Please **don't** open public issues for security problems — see
[SECURITY.md](./SECURITY.md) for the disclosure process.

## License

Unless a repo says otherwise, contributions are MIT-licensed. By opening
a PR you confirm you have the right to submit the code and you agree to
license it under the same terms as the repo.
