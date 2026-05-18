# Security Policy

## Supported versions

xgoose is a small, fast-moving project. Only the most recent release of
each component is supported with security fixes:

| Component | Supported |
| --- | --- |
| `xgoose-extension-chrome` (Chrome Web Store) | latest |
| `xgoose-extension-firefox` (Firefox Add-ons) | latest |
| `xgoose-extension-safari` (App Store) | latest |
| `xgoose.org` web app + AI gateway | always-current |

## Reporting a vulnerability

**Please don't open a public issue.** Email <dev@xgoose.org> with:

- A clear description of the issue and the impact you think it has.
- Steps to reproduce (a minimal proof-of-concept is ideal).
- Whether you'd like to be credited in the disclosure note.

You should get a reply within **72 hours**, usually sooner. We'll work
with you on a fix and a coordinated disclosure timeline; in most cases
that means shipping a patch release within 7 days for client-side issues,
and same-day for server-side issues.

## Scope

In scope:

- The agent core, skill runtime, page controller, and chat UI shipped in
  any extension or via `<script src="https://xgoose.org/embed.js">`.
- `xgoose.org` (Next.js app, Worker API, D1 schema).
- First-party skills in
  [`xgoose-skills`](https://github.com/xGoose-dev/xgoose-skills).

Out of scope:

- Third-party / community skills — please report those to the skill
  author directly. We will still help you reach them.
- Bugs that require an attacker to already control the user's browser or
  the page they're chatting about.
- Findings that rely on outdated browser versions no longer receiving
  vendor security updates.

## Safe harbor

We won't pursue legal action against good-faith security research that
follows this policy. Please don't run automated scans against
`xgoose.org` or `api.xgoose.org` — DM us instead and we'll set you up
with a safe target.
