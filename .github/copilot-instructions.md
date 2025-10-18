Project: TENUP — static marketing / design showcase

This repository is a small static website (single HTML file + static assets) that documents a mobile product concept called TENUP. The goal of these instructions is to help AI coding agents become productive quickly when editing, extending, or reviewing this project.

Key points (quick):
- Single entry: `landing_page.html` is the authoritative source. It includes all CSS (inline <style>), small JS for UI interactions, and references to static images in `assets/`.
- No build system, package.json, or tests present. Changes are simple file edits and commit/push.

Repository structure (relevant files):
- `landing_page.html` — main HTML document. Contains: Tailwind CDN import, Google Fonts, inline CSS variables for colors, and a DOMContentLoaded script for menu toggle and scroll-based nav highlighting.
- `assets/` — images used by the page (e.g., `panda.png`, `star.gif`). Keep filenames and relative paths intact when editing HTML.

Architecture & design decisions (observable):
- Single-page, static marketing/design document. Styling is done with a mix of Tailwind utility classes (via CDN) and hand-written CSS inside the file (CSS variables for core colors: `--primary-green-dark`, `--primary-green-light`, `--accent-orange`, `--background`, `--neutral-dark`). Prefer editing those variables for global color changes.
- Small, dependency-free JS at the bottom of `landing_page.html` for progressive enhancement (mobile menu toggle and IntersectionObserver-based active nav). Avoid removing the IntersectionObserver unless replacing it with equivalent behavior.
- Components are not extracted into partials; edits are done in-place. Keep the current layout patterns: header/nav, hero (with mascot), sections (project-details, problem, personas, user-flow, wireframes, prototype, design-system).

Developer workflows and commands:
- Local preview: open `landing_page.html` in a browser. For a simple local server (recommended for correct file serving), run a static server from the repo root. Example (macOS / zsh):
  - python3 -m http.server 8000  # serves current directory at http://localhost:8000
- No build step: editing and saving `landing_page.html` and assets is sufficient. Use normal git commits to publish changes.

Conventions and patterns to follow:
- Keep images under `assets/` and reference them with relative paths (e.g., `assets/panda.png`). Changing filenames requires updating all uses.
- Global styling: prefer changing CSS variables near the top of `landing_page.html` for consistent color/brand updates. Avoid scattering new hard-coded colors.
- Tailwind usage: uses CDN; additional utility classes can be added inline, but avoid adding a Tailwind build config unless the repo is migrated to a structured build process.
- Inline scripts: small DOMContentLoaded block should remain near the bottom of the file. If you add more JS, keep it unobtrusive and avoid introducing heavy frameworks.

Examples and quick edits:
- To change the primary brand color, edit the `--primary-green-dark` variable in the <style> block near the top of `landing_page.html`.
- To add another nav item, add an <a> with class `nav-link` inside the desktop nav and add the same link to the mobile menu; ensure the target section has a matching `id`.
- To add an asset, place it in `assets/` and reference it from `landing_page.html` with `src="assets/<filename>"`.

Integration points & external deps:
- Tailwind CSS via CDN: `https://cdn.tailwindcss.com` (present).
- Google Fonts: Poppins via fonts.googleapis.com.
- No backend, APIs, or CI configured. If you add integrations, document them in README or a new CI workflow.

When to ask for clarification:
- If you're planning to introduce a build system (npm/Tailwind CLI, bundler, etc.), ask before converting inline styles to a compiled pipeline.
- If adding interactive app logic (state, routing), confirm whether to keep this repo static (marketing) or convert to app repo.

Safety and formatting:
- Preserve the file's indentation and style. Edits should be minimal and local to the intent (color, content, image swaps).
- Run a local browser preview after changes; no automated tests are present.

If anything in these instructions is unclear or you need more project history (design rationale, original assets), tell me what to add and I will iterate.
