# vs-code-stuff

All the stuff that I want to keep here in case I change computer. Nothing major though, just some set ups.

---

## What is in this repo

| Path | Purpose |
|------|---------|
| `vscode/settings.json` | Portable **Visual Studio Code** look: layout, fonts, `workbench.colorCustomizations`, `editor.tokenColorCustomizations`, icon theme (`vs-seti`). |
| `vscode/extensions.txt` | Optional extension IDs to install on a new machine. |
| `web/cursor-web-agents.user.css` | **Unofficial** browser **Stylus** style to get a *similar* navy / lime / coral look on the **Cursor website** (Agents, marketing pages) — *not* the same as the desktop app (there is no official “sync theme to web” yet). |

The desktop look is 100% standard `settings.json` (no custom CSS, no pentagram in this bundle).

---

## VS Code (desktop) — new Mac / Windows / Linux

1. Install [Visual Studio Code](https://code.visualstudio.com/).

2. Back up your current user settings (optional).

3. **macOS**

   ```bash
   cp vscode/settings.json ~/Library/Application\ Support/Code/User/settings.json
   ```

4. **Windows** — `%APPDATA%\Code\User\settings.json`  
5. **Linux** — `~/.config/Code/User/settings.json`

6. Optional extensions:  
   `xargs -L1 code --install-extension < vscode/extensions.txt`  
   (or use the `code` binary path for your OS.)

7. Restart VS Code.

---

## Cursor (desktop) — same palette

Use the same `vscode/settings.json` with:

`~/Library/Application Support/Cursor/User/settings.json` (macOS).

Cursor’s bundled themes (e.g. “Cursor Dark”) may need **theme-scoped** `workbench.colorCustomizations` — your local file may already be set up that way. Restart Cursor after copy.

---

## Cursor web (Agents) — *similar* colors in the **browser**

The **web** product ([cursor.com](https://cursor.com) and subdomains) is a **separate** surface. There is no supported way to “log in and pull my editor theme” from an API. The practical workaround is a **Stylus** user style:

1. Install the [Stylus](https://add0n.com/stylus.html) extension (Chrome / Firefox / Edge).

2. Open Stylus → **Write new style** → **Import** (or paste) the file  
   `web/cursor-web-agents.user.css`.

3. Save, enable, and set it to run on:
   - `https://cursor.com/*`
   - `https://*.cursor.com/*`  
   (Add other hosts you use, e.g. a preview or `*.cursor.sh`, by duplicating the top `@-moz-document` block in that file.)

4. **Expect imperfection:** the site will change. If something is still white or wrong, use **DevTools** → pick a node → add or tighten selectors in the user CSS.

5. This does **not** change Cursor’s servers—only *your* browser’s rendering.

---

## For another agent

- **Desktop theme source of truth:** `vscode/settings.json`.
- **Web overlay:** `web/cursor-web-agents.user.css` + Stylus.
- Re-copy `settings.json` from your machine and commit when the look drifts.

## License

Personal configuration; use however you like.
