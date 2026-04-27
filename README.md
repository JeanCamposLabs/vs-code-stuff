# vs-code-stuff

All the stuff that I want to keep here in case I change computer. Nothing major though, just some set ups.

---

Repository: [github.com/JeanCamposLabs/vs-code-stuff](https://github.com/JeanCamposLabs/vs-code-stuff)

Portable **Visual Studio Code** look: dark navy editor (`#0a1628`), lime accents (`#5ce65c` / `#7ef47e`), coral highlights, top activity bar, Menlo/Monaco, token rules—plus an **optional** Stylus layer for the **Cursor website** (Agents) in the browser.

## What is included

| Path | Purpose |
|------|---------|
| `vscode/settings.json` | Window layout, fonts, `workbench.colorCustomizations`, `editor.tokenColorCustomizations`, icon theme (`vs-seti`), etc. |
| `vscode/extensions.txt` | Optional extension IDs. Custom CSS / Fix Checksums are omitted for a clean install. |
| `web/cursor-web-agents.user.css` | **Unofficial** browser style (Stylus) for a *similar* palette on `cursor.com` — *not* an official Cursor feature. |

The desktop look is **100% standard** `settings.json` (no patched app files in this bundle).

---

## Apply on a new Mac (VS Code)

1. Install [Visual Studio Code](https://code.visualstudio.com/).
2. **Back up** your current `settings.json` if needed.
3. Clone this repo, then:

   ```bash
   REPO="$HOME/path/to/vs-code-stuff"
   cp "$REPO/vscode/settings.json" \
      ~/Library/Application\ Support/Code/User/settings.json
   ```

4. Restart VS Code (**Cmd+Q**, reopen).

5. **Extensions** (optional):

   ```bash
   xargs -L1 code --install-extension < "$REPO/vscode/extensions.txt"
   ```

## Windows / Linux

- **Windows:** `%APPDATA%\Code\User\settings.json`
- **Linux:** `~/.config/Code/User/settings.json`

Copy `vscode/settings.json` there.

## Cursor (desktop)

Use the same file at:

`~/Library/Application Support/Cursor/User/settings.json`

Cursor’s default themes are named **“Cursor Dark”**, **“Cursor Dark Midnight”**, etc. Theme-scoped `workbench.colorCustomizations` may be required; copy from a machine that already looks right, then restart Cursor.

---

## Cursor web (Agents) — browser only

The **website** is a different product: there is **no** official “import my editor theme” API. The workaround is a **Stylus** userstyle:

1. Install [Stylus](https://add0n.com/stylus.html).
2. Import `web/cursor-web-agents.user.css` (or paste its contents into a new style).
3. Enable it for `https://cursor.com/*` and `https://*.cursor.com/*` (add other hosts you use by editing the `@-moz-document` lines).
4. Expect to tweak selectors after Cursor ships UI changes; use DevTools if something stays wrong.

This only affects **your** browser, not other users or Cursor’s servers.

---

## For another agent

- **Desktop:** `vscode/settings.json` is the source of truth.
- **Web:** `web/cursor-web-agents.user.css` + Stylus.
- Re-copy and commit when the look drifts.

## License

Personal configuration; use however you like.
