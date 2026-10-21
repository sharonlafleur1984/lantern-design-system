# Light and glass

**Last updated:** October 21, 2026

One page for the light and the glass: when a component is see-through, when it is Solid with a glass edge, where the light comes from, how bright it is. Decided as D70 on Oct 20, 2026, from a draft Sharon reviewed in two rounds ([the saved review page](../blob/main/docs/references/light-and-glass-rules/index.html), with pictures). It gathers D57 to D64 and D69 and replaces the "only on art" part of D64.

Rules 2, 4, 6, 7 and 8 describe where the code goes. Today glass is still see-through only on art, and five components have no Glass switch. The cursor light is dark-mode only, and the light on a plain page is white. Each becomes its own pull request.

## The rules

1. **One light per page, and every component with a surface answers it.** Each component with a surface wears the glass edge by default (D69). Its rim is brightest where it faces the light, with a glint where the light leaves, and its shadow falls away from the light. The same tokens do this in light and dark mode, so a component never has to know which mode it is in. Text, Link, Separator, Tabs and icons have no surface and stay as they are.
   - **No base line under the rim on buttons, cards, tiles, action tiles and tags** (Sharon's pick from three close-ups). The lit rim and the shadow are their edge. WCAG asks for a 3:1 boundary only where the boundary is what tells you a thing is a control. A labelled button does not need one.
   - **Fields and boxes keep a 3:1 line** under their rim: Select, the Checkbox box, the Switch track and the Toggle button group. Their boundary is what marks them. The contrast test checks those four.
2. **Glass bends what is behind it, wherever it is.** A Glass component is see-through on art, on a photo and on a plain page alike. A Solid component keeps its fill and wears the edge. Which one a component uses is your choice for each use, never the system's guess. A plain color has nothing to bend, so Glass on a plain page shows as its rim, highlight, shade and shadow over that color.
3. **Words never bend.** Text and icons sit on top of the glass and stay sharp. Glass text passes 4.5:1 against the lightest and darkest colors behind it, art or page. Tests check it for every theme and mode.
4. **Every component with a surface can be Glass or Solid.** Button, Card, Tile, Action tile, Popover, Select, Checkbox, Switch, Tag and Toggle button group all offer both. Solid is the default. You pick Glass where you want it, and the text check in rule 3 keeps values readable there.
   - **A third look, Frosted ([#99](https://github.com/sharonlafleur1984/lantern-design-system/issues/99)): the background shows through blurred and milky, with the edge, so text stays readable on busy art. Popover has it first (lantern-code #159, Oct 21); the other components follow under #99. Both glasses use the glass ink on art, and the contrast test checks it over each theme's art.
5. **Settings win over looks, and the Solid look is designed, not a fallback.** Reduce transparency or Increase contrast, from the device or from Settings, turns every Glass component Solid with the edge. It is still lit by the page's light, with the same rim and shade, so it reads as the same family. Forced colors keep only the border. Reduce motion keeps the light still. [#8](https://github.com/sharonlafleur1984/lantern-design-system/issues/8) reviews every component in Increase contrast, all six looks, with pictures.
6. **One light, brighter at night and softer by day, with one setting: Off, On or Follow.** Every theme has one light. In dark mode it is bright, as it is today. In light mode it is soft. It rests at the light tokens, `light-from-right` and `light-top`; Sunrise's follows the time of day. In Settings the light has three states, in light or dark mode. Off: no light, every surface at rest. On, the default: the product's source is lit and stays where it is. Follow: the light goes where the person points, riding the cursor, and the source dims while it is away. "Follow" is a draft name; Carried, Held and In hand also fit. This replaces D58's dark-mode-only cursor light.
7. **Each product has a visible source for its light. The Orb is the light wherever a person moves it.** At rest the light is the product's own source: the centre of Spotlight's wheel, Sunrise's Let's chat orb, and Fireside's logo. Fireside's glows with the warmer Fireside light and draws no orb. The source is dim by day and bright at night. The Orb is that same light the moment a person moves it: dragged in Storybook's glass stories, playgrounds and Try it out windows, and following the pointer on any product page when the setting is Follow. Then every surface answers the moving light instead of the resting source.
8. **The light takes its color from what it falls on.** A lamp on a white wall shows as the wall's own color made brighter, so the light is never a white picture laid on top. On art it brightens the pattern it falls on (D59). On a plain page it takes only the page's own tint and shows through strength and falloff: the rims it hits go brighter, the shadows it casts fall away from it, and nothing turns the theme's color. That is what makes it show on a white Spotlight page instead of vanishing. Two mocks that tinted the light with the theme's red read as "a light bulb with a filter" and were dropped.
9. **Every component near the light reacts the same way, whatever the source.** Whether the light is the product's resting source, the time of day, the cursor or a dragged Orb, every surface near it lights the same way from the same tokens, by day and at night.

## Shadows

Decided as D73 on Oct 20, 2026 ([the saved review page](../blob/main/docs/references/shadow-rules/index.html), with mocks).

1. **One light casts every shadow.** A shadow is the glass cast from the page's light (D69): away from the light, in the theme's cast color, at the theme's strength. No component has a shadow of its own. The static tokens `shadow-rest`, `shadow-hover` and `shadow-float` retire once the last component has moved.
2. **Three heights, and nothing in between.** Resting: in the page's flow, a short cast and a tight contact shadow. Raised: lifted toward the light, twice the distance and wider; a hover or a press does this. Floating: above the page, four times the distance, widest and faintest; anything React Aria floats.
3. **Higher is farther, softer and fainter.** Each height scales the same cast. The direction never changes within a page.

| Height | Distance | Blur | Cast tint | Contact |
|---|---|---|---|---|
| Resting | 1 × the theme's cast distance | 1 × | 1 × | Yes |
| Raised | 2 × | 1.5 × | 1.2 × | Yes, fainter |
| Floating | 4 × | 2 × | 1.4 × | No |

4. **Night is stronger, day is softer, and the theme sets the tint.** The heights scale the theme's values and never add a color of their own.
5. **Every component has one height, and the floating ones are React Aria's.** Floating: Popover, Select's menu, Menu, Tooltip, Dialog, Modal, the Settings sheet when open. Resting: Card, Tile, Action tile, Callout, Select's field, the Checkbox box, the Switch track, Tag, Toggle button group. Raised: any of those while hovered or pressed, and the Orb's ball. A component never picks a shadow; it says its height, and the height picks the shadow from the light.
6. **Settings change the strength, never the direction.** Increase contrast makes the cast stronger and adds the 3:1 line under the rim (D69). Reduce transparency changes nothing about shadows. Reduce motion keeps the light still. Forced colors draw borders instead.
7. **One place in the code, checked by a test.** The heights are classes on the shared glass edge, and a test fails when a component stylesheet draws a `box-shadow` that is not the glass cast.

## Component rules and product rules, kept apart

Two levels, each with its own home.

- **Component rules** say what a component can do: every look, every state, every option, with plain labels. They live on the Components pages in Storybook and on this page. Rules 1 to 5 and 9 are component rules.
- **Product rules** say what one product chooses: where its light is and what it looks like, which components are Glass on which pages, its art, how bright its light is by day and at night. They live on [Themes](Themes), one section per product, and in Storybook under a Products section with one page per product. Rules 6 to 8 set the shared shape; each product fills in its own values.
- **The direction:** the products drive the changes. When Life Hub, After Graduation or the toolkit needs something a component cannot do, that need becomes the component's new option, built so all three products can use it, and the product then picks it up. A product page never adds an option on its own, so no solution stays locked to one project.

Today Storybook has Components, Foundations and Explorations. The Products section is new, and the product-only stories now under Explorations (Sunrise's page shell, the sky header) would move there.

## Why glass pages open slowly, and the fix

Measured on Oct 20, 2026 on a Mac in Chromium on the built Storybook, light mode, with the browser's own profiler. The slow part is not the see-through glass. It is the light: the renderer that lights the background (D59) and the drawing of each orb (D57) run on the page's main thread as soon as the page opens, in one freeze of about two seconds, before anything can be clicked.

| Story | Ready after | Longest freeze | Where the time goes |
|---|---|---|---|
| Sunrise page shell | 2.7 s | 2.0 s | 1.0 s making the renderer's drawing surface, 0.8 s drawing the orb |
| Sunrise glass cards, all areas | 2.8 s | 1.8 s | 1.0 s the drawing surface, 0.5 s the orb, 0.2 s the lit background |
| Button, glass on every marble | 3.1 s | 1.7 s | 1.0 s the drawing surface, 0.5 s the orb |
| Spotlight page shell, see-through tiles, no renderer light | 0.8 s | 0.16 s | 0.09 s painting the glass |

Once a page is open, every story still draws at 60 frames a second, light moving or not.

**The fix Sharon agreed to**

1. Show the page with its CSS glow first.
2. Draw the orb and the lit background in the browser's next idle moment, and fade them in.

The freeze moves off the opening, so the page is usable in under a second. That is an estimate; the drawing still takes the same time, only later.

Two more, later, if needed: make the drawing cheaper (no extra smoothing, no kept drawing buffer, the orb picture as a bitmap, the lit background at half resolution), and draw it in a worker so there is no freeze at all.

## Where to look

- The saved review page with every picture, including the three edge close-ups and the real Orb on a plain page: [docs/references/light-and-glass-rules](../blob/main/docs/references/light-and-glass-rules/index.html).
- The decisions this page gathers: D57, D58, D59, D64, D69 and D70 in [Decisions](Decisions).
- The issues it answers: [#49](https://github.com/sharonlafleur1984/lantern-design-system/issues/49) and [#4](https://github.com/sharonlafleur1984/lantern-design-system/issues/4).
