# CLAUDE.md

Start here. This file tells Claude (and any developer) where everything lives, so only the needed file gets opened.

## What this is

Lantern design system: the plan and docs for one shared design system with a theme for each of Sharon's products. This public repo holds the wiki, the issues, the milestones and the project board. The code lives in the private [lantern-code](https://github.com/sharonlafleur1984/lantern-code) repo.

## Rules

- **How I work:** follow [how-i-work](https://github.com/sharonlafleur1984/how-i-work) for the process and skills.
- **One home for the plan.** The roadmap, decisions, backlog and every wiki page live here and nowhere else. lantern-code links here; it never keeps its own copy.
- **Public repo.** No personal data and no client work. Say "a client project," never the client's name.
- **Every fact needs a source link,** or a label saying it's an estimate.
- **Ask before changing or deleting anything.** A recommendation is not approval.
- **Wiki pages are edited in `docs/wiki/`,** never in the GitHub Wiki tab. They publish on every merge to main.
- **Code decisions get two pull requests.** The code and its Storybook docs go in lantern-code, and the Decisions entry goes here. Each links to the other.
- **Every issue names its problem.** Each one has "Problem to solve" and "What success looks like."
- **Big work is a parent issue.** Its sub-issues are in the order they depend on each other.
- **Pull requests close their issue.** A pull request in lantern-code says "Fixes sharonlafleur1984/lantern-design-system#N."
- **Every commit names its Claude session.** End each commit message with `Claude-Session:` and the link to the session that made it.
- **Main is protected.** Changes reach main only through a pull request ([cheat sheet](https://github.com/sharonlafleur1984/how-i-work/blob/main/templates/github-ruleset.md)). Remind Sharon if the "Protect main" ruleset is missing.
- **Finish with a pull request.** Pushed work always gets one, even when it's small.

## Where everything is

Start with [`docs/wiki/Documents.md`](docs/wiki/Documents.md): every document in this project and when to open it. When you add or remove a document, update its row there and in the private Notion index in the same pass.

## Skills to use

- `product-manager` for roadmap, backlog and status
- `product-designer` for design, page structure and the component library
- `ux-writer` for any words people will read, with [`docs/voice.md`](docs/voice.md) for this project's voice
- `product-engineer` for any code work, in lantern-code
- `working-with-sharon` for how to write to Sharon

## Outside the repo (private)

- Code: [lantern-code](https://github.com/sharonlafleur1984/lantern-code)
- Project entry: Notion, Projects, "Design system"
