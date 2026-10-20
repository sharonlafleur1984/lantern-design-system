# Roadmap

**Last updated:** October 20, 2026

| Now | Next | Later |
|---|---|---|
| **Can reviewers trust every component page?** Button's page is the template. Every other page is brought up to it, with that component's open bugs fixed in the same pass, so each one is reviewed once ([Every page matches Button's](https://github.com/sharonlafleur1984/lantern-design-system/milestone/10), [#86](https://github.com/sharonlafleur1984/lantern-design-system/issues/86)) | **Can apps install the next version and trust the docs?** A release that ships the right version ([Release 0.4.0](https://github.com/sharonlafleur1984/lantern-design-system/milestone/5)), and a wiki that says what the code does ([Docs and wiki](https://github.com/sharonlafleur1984/lantern-design-system/milestone/4), [#92](https://github.com/sharonlafleur1984/lantern-design-system/issues/92)), Nov 12 | **Can people use lists and fine controls?** Slider, meter, grid list, toggle button, table, disclosure, toast, dialog, avatar and drop zone ([#61](https://github.com/sharonlafleur1984/lantern-design-system/issues/61)) |
| **Can new screens be built from Lantern?** The rules for when a part is solid or glass ([Light and glass rules](https://github.com/sharonlafleur1984/lantern-design-system/milestone/8), Oct 25), then the icon set, popover, page tabs, menu and tooltip ([First new components](https://github.com/sharonlafleur1984/lantern-design-system/milestone/9), Oct 30) | **Is Lantern easy to change?** One theme is one folder, no unused tokens, consistent props and quiet builds ([Code health](https://github.com/sharonlafleur1984/lantern-design-system/milestone/6), Nov 19) | **Can Lantern grow without Sharon writing code?** A theme kept in its own repo ([#74](https://github.com/sharonlafleur1984/lantern-design-system/issues/74)), the quick edit page ([#75](https://github.com/sharonlafleur1984/lantern-design-system/issues/75)), and a Lantern library in Figma with a mode for each theme |
| **Can everyone use it, and does a change in one theme stay there?** Windows high contrast and Increase contrast work everywhere ([High contrast](https://github.com/sharonlafleur1984/lantern-design-system/milestone/1), Oct 29). Contrast passes in every theme ([#89](https://github.com/sharonlafleur1984/lantern-design-system/issues/89)) and Reduce motion works everywhere ([#90](https://github.com/sharonlafleur1984/lantern-design-system/issues/90)), in [Accessibility AA](https://github.com/sharonlafleur1984/lantern-design-system/milestone/2), Nov 5. The screenshot check catches every change ([#91](https://github.com/sharonlafleur1984/lantern-design-system/issues/91)), in [Checks that catch it](https://github.com/sharonlafleur1984/lantern-design-system/milestone/3), Nov 5 | **Can people fill in forms and pick options?** Radio group, text field, search field and a list of labels and values ([Form parts](https://github.com/sharonlafleur1984/lantern-design-system/milestone/11), [#56](https://github.com/sharonlafleur1984/lantern-design-system/issues/56)), the toolbar and tree that designer-toolkit's shell waits on, and the Settings menu ([#2](https://github.com/sharonlafleur1984/lantern-design-system/issues/2)) | **Is the pointer the light in dark mode?** Illuminate (D58) and Storybook's Light: On (D63, on the `claude/light-control` branch) |

Every component is built from Lantern's own parts, so a part comes before anything that nests it. Icons and popovers come first, because menus, tooltips and icon buttons use them. Callout, Link, Tag and Select switch to the icon set right after it ([#76](https://github.com/sharonlafleur1984/lantern-design-system/issues/76)). After that, the parts most screens need come first.

## Milestones

Each milestone is a finish line, with the date it's aiming for.

| Milestone | Done when | Timing |
|---|---|---|
| [Light and glass rules](https://github.com/sharonlafleur1984/lantern-design-system/milestone/8) | Sharon has approved one page of rules for light and glass, and every theme follows them in Storybook | Aiming for Oct 25, 2026 |
| [High contrast](https://github.com/sharonlafleur1984/lantern-design-system/milestone/1) | Windows high contrast mode and the Increase contrast setting work in every theme and mode | Aiming for Oct 29, 2026 |
| [First new components](https://github.com/sharonlafleur1984/lantern-design-system/milestone/9) | The icon set, popover, page tabs, menu and tooltip pass the Storybook gate in every theme, light and dark | Aiming for Oct 30, 2026 |
| [Accessibility AA](https://github.com/sharonlafleur1984/lantern-design-system/milestone/2) | Every component meets WCAG 2.2 AA in every theme, light and dark: contrast, focus, errors, states and motion | Aiming for Nov 5, 2026 |
| [Checks that catch it](https://github.com/sharonlafleur1984/lantern-design-system/milestone/3) | The screenshot check is required to merge, dark mode is screenshotted, the token lock covers the built CSS, and the Lantern build runs on every pull request | Aiming for Nov 5, 2026 |
| [Docs and wiki](https://github.com/sharonlafleur1984/lantern-design-system/milestone/4) | The wiki, README and Storybook pages say what the code does, and every link works | Aiming for Nov 12, 2026 |
| [Release 0.4.0](https://github.com/sharonlafleur1984/lantern-design-system/milestone/5) | The next release ships the right version, installs cleanly and has a safe workflow | Aiming for Nov 12, 2026 |
| [Code health](https://github.com/sharonlafleur1984/lantern-design-system/milestone/6) | One theme is one folder, no unused tokens, consistent props and quiet builds | Aiming for Nov 19, 2026 |
| [Every page matches Button's](https://github.com/sharonlafleur1984/lantern-design-system/milestone/10) | Every component's page matches Button's, with that component's open bugs fixed in the same pass | Not set yet |
| [Form parts](https://github.com/sharonlafleur1984/lantern-design-system/milestone/11) | Radio group, text field, search field, a list of labels and values, and the Settings menu pass the Storybook gate in every theme, light and dark | Not set yet |

<details>
<summary>Already done</summary>

| Milestone | Done when | Timing |
|---|---|---|
| [Component page template](https://github.com/sharonlafleur1984/lantern-design-system/milestone/7) | Reviewers can find their way around the component page: controls, Try it out and the upper menu, mocked up and reviewed first | Done, Oct 20, 2026 |
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
| New components land before the checks are in place | A change made for one theme breaks another, and nobody notices | Running the screenshot checks ([#21](https://github.com/sharonlafleur1984/lantern-design-system/issues/21), [#22](https://github.com/sharonlafleur1984/lantern-design-system/issues/22)) before the new components land on Oct 30, and the rest of the checks by Nov 5. Owner: Claude |
| The glass build stays slow and complicated | Every component that offers glass pays for it in speed | Deciding in the glass review which parts offer glass at all. Owner: Sharon |
| A client's site can't run React | Lantern's components can't be used there, and only its tokens carry over | Confirming the client's platform before building parts only that client needs. Owner: Sharon |

[Dashboard](Home) · [Decisions](Decisions) · [Issues](https://github.com/sharonlafleur1984/lantern-design-system/issues) · [Project board](https://github.com/users/sharonlafleur1984/projects/8) · [Storybook](https://lanterndesignsystem.netlify.app/)
