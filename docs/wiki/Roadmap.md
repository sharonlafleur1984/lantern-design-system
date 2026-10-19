# Roadmap

**Last updated:** October 19, 2026

| Now | Next | Later |
|---|---|---|
| **Does one theme's change break another?** The checks catch it before anything merges ([Checks that catch it](https://github.com/sharonlafleur1984/lantern-design-system/milestone/3)) | **Can people fill in forms and pick options?** Radio group, text field, search field and a list of labels and values ([#56](https://github.com/sharonlafleur1984/lantern-design-system/issues/56)) | **Can people use lists and fine controls?** Slider, meter, grid list, toggle button, table, toolbar, tree, disclosure, toast, dialog, avatar and drop zone ([#61](https://github.com/sharonlafleur1984/lantern-design-system/issues/61)) |
| **When is a part solid or glass?** One page of rules for glass and how bright the light is, with the glass review ([#49](https://github.com/sharonlafleur1984/lantern-design-system/issues/49), [#4](https://github.com/sharonlafleur1984/lantern-design-system/issues/4)) | **Can a theme live outside Lantern?** A private theme, kept in its own repo, is built and checked like the others | **Can Life Hub use it?** Life Hub loads its theme and builds its pages from these components |
| **Can new screens be built from Lantern?** The first new components, each built from Lantern's own parts: an [icon set](https://github.com/sharonlafleur1984/lantern-design-system/issues/1), popover, tabs that go to other pages, menu and tooltip ([#50](https://github.com/sharonlafleur1984/lantern-design-system/issues/50)) | **Can Sharon change Lantern without writing prompts?** The quick edit page, built from the approved mockup | **Does Figma match the code?** A Lantern library in Figma, with a mode for each theme |

Every component is built from Lantern's own parts, so a part comes before anything that nests it. Icons and popovers come first, because menus, tooltips and icon buttons use them. Callout, Link, Tag and Select switch to the icon set right after it ([#76](https://github.com/sharonlafleur1984/lantern-design-system/issues/76)). After that, the parts most screens need come first.

## Milestones

Each milestone is a finish line, with the date it's aiming for.

| Milestone | Done when | Timing |
|---|---|---|
| [Component page template](https://github.com/sharonlafleur1984/lantern-design-system/milestone/7) | Reviewers can find their way around the component page: controls, Try it out and the upper menu, mocked up and reviewed first | Aiming for Oct 22, 2026 |
| [Light and glass rules](https://github.com/sharonlafleur1984/lantern-design-system/milestone/8) | Sharon has approved one page of rules for light and glass, and every theme follows them in Storybook | Aiming for Oct 25, 2026 |
| [High contrast](https://github.com/sharonlafleur1984/lantern-design-system/milestone/1) | Windows high contrast mode and the Increase contrast setting work in every theme and mode | Aiming for Oct 29, 2026 |
| [Checks that catch it](https://github.com/sharonlafleur1984/lantern-design-system/milestone/3) | The screenshot check is required to merge, dark mode is screenshotted, the token lock covers the built CSS, and the Lantern build runs on every pull request | Aiming for Nov 5, 2026 |
| [Accessibility AA](https://github.com/sharonlafleur1984/lantern-design-system/milestone/2) | Every component meets WCAG 2.2 AA in every theme, light and dark: contrast, focus, errors, states and motion | Aiming for Nov 5, 2026 |
| [Docs and wiki](https://github.com/sharonlafleur1984/lantern-design-system/milestone/4) | The wiki, README and Storybook pages say what the code does, and every link works | Aiming for Nov 12, 2026 |
| [Release 0.4.0](https://github.com/sharonlafleur1984/lantern-design-system/milestone/5) | The next release ships the right version, installs cleanly and has a safe workflow | Aiming for Nov 12, 2026 |
| [Code health](https://github.com/sharonlafleur1984/lantern-design-system/milestone/6) | One theme is one folder, no unused tokens, consistent props and quiet builds | Aiming for Nov 19, 2026 |
| First new components | The icon set, popover, page tabs, menu and tooltip pass the Storybook gate in every theme, light and dark | Not set yet |

<details>
<summary>Already done</summary>

| Milestone | Done when | Timing |
|---|---|---|
| Themes reviewed | Sharon has approved the first two themes | Done, Oct 7, 2026 ([Decisions](Decisions)) |
| Storybook published | A public link opens Storybook with the theme switcher | Done ([Storybook](https://lanterndesignsystem.netlify.app/)) |
| First components | Button, card and chip pass the Storybook gate in every theme | Done, with 13 components and a Settings pattern on React Aria |
| After Graduation uses it | After Graduation installs a pinned version | Done, [v0.2.0](https://github.com/sharonlafleur1984/after-graduation/blob/main/package.json) |
| Third theme | Fireside passes the theme tests and shows in Storybook | Done, Oct 14, 2026 ([Decisions](Decisions)) |
| Code and docs split | The code is private in lantern-code; the docs, wiki and issues are public here | Done, Oct 18, 2026 |

</details>

## What could go wrong

These are the few things that could sink the plan, and what's being done about each.

| If this happens... | ...then | So we're... |
|---|---|---|
| New components land before the checks are in place | A change made for one theme breaks another, and nobody notices | Finishing the checks first. Owner: Claude |
| The glass build stays slow and complicated | Every component that offers glass pays for it in speed | Deciding in the glass review which parts offer glass at all. Owner: Sharon |
| A client's site can't run React | Lantern's components can't be used there, and only its tokens carry over | Confirming the client's platform before building parts only that client needs. Owner: Sharon |

[Dashboard](Home) · [Decisions](Decisions) · [Issues](https://github.com/sharonlafleur1984/lantern-design-system/issues) · [Project board](https://github.com/users/sharonlafleur1984/projects/8) · [Storybook](https://lanterndesignsystem.netlify.app/)
