# Working rules for Claude

- Never ask the user to do something manually that you can do for them. Check your MCP servers, tools, and
  connectors; if you can do it for them, always do it yourself for the user.
- No hallucinations: check facts, files, links and results with a tool before stating them; say plainly what was not checked.

## UI design toolkit (saved Nov 24 2026 from Rachael's list; every repo checked to exist)

Use these when building or polishing any interface. **Fit check first:** the Recruiter Hub and the Universal Pay
Package Calculator are single built HTML files with no React and no build-time CSS framework. React-only
libraries (marked **React**) cannot go into them as-is; borrow their design ideas, or use them only in a new
React app. Adding any library or CDN script to the Hub is a change Rachael approves first, and it must never
touch pay math, element IDs or saved-data keys (see recruiter-hub-5.1/CLAUDE.md in rachaelmast/skybridge-healthcare-tools-portal).

| Need | Repo | Works in plain HTML? |
|---|---|---|
| Design skill with a handcrafted feel | [anthropics/skills](https://github.com/anthropics/skills) (`skills/frontend-design`) | Yes, it is guidance |
| Review and polish a design | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | Yes, it is guidance |
| Owned, copy-in components | [shadcn-ui/ui](https://github.com/shadcn-ui/ui) | React |
| Accessible dialogs, menus, popovers | [radix-ui/primitives](https://github.com/radix-ui/primitives) | React |
| ⌘K command menu | [dip/cmdk](https://github.com/dip/cmdk) | React |
| Glow, rays, marquee effects | [magicuidesign/magicui](https://github.com/magicuidesign/magicui) | React (CSS ideas portable) |
| Stacking toasts | [emilkowalski/sonner](https://github.com/emilkowalski/sonner) | React |
| Native-feeling mobile drawers | [emilkowalski/vaul](https://github.com/emilkowalski/vaul) | React |
| Utility CSS | [tailwindlabs/tailwindcss](https://github.com/tailwindlabs/tailwindcss) | Yes (needs a build step or the CDN) |
| Themes with one class | [saadeghi/daisyui](https://github.com/saadeghi/daisyui) | Yes (Tailwind plugin) |
| Line icons (5,900+) | [tabler/tabler-icons](https://github.com/tabler/tabler-icons) | Yes, plain SVG |
| Component catalog with every state | [storybookjs/storybook](https://github.com/storybookjs/storybook) | Yes (has an HTML renderer) |
| KPI cards, dashboards | [tremorlabs/tremor](https://github.com/tremorlabs/tremor) | React |
| Charts | [recharts/recharts](https://github.com/recharts/recharts) | React |
| 120+ components and hooks | [mantinedev/mantine](https://github.com/mantinedev/mantine) | React |

Order of work: skill → component → style → animation → chart → review with Impeccable.
