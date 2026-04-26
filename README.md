# vs-code-stuff

All the stuff that I want to keep here in case I change computer. Nothing major though, just some set ups.

---

Portable **Visual Studio Code** UI setup: dark navy editor, lime accents, coral highlights, top activity bar, and the same token colors—so a new machine can match this look quickly.

Repository: [github.com/JeanCamposLabs/vs-code-stuff](https://github.com/JeanCamposLabs/vs-code-stuff)

## What is included

| Path | Purpose |
|------|---------|
| `vscode/settings.json` | Window layout, fonts, `workbench.colorCustomizations`, `editor.tokenColorCustomizations`, icon theme (`vs-seti`), etc. |
| `vscode/extensions.txt` | Common extensions from the machine this was captured on (optional). **Custom CSS Loader** and **Fix Checksums** are omitted so a fresh install stays stock. |

The look is **100% standard** `settings.json` (no custom CSS, no patched app files).

## Apply on a new Mac

1. Install [Visual Studio Code](https://code.visualstudio.com/).

2. **Back up** your current user settings (optional but wise):

   ```bash
   cp ~/Library/Application\ Support/Code/User/settings.json \
      ~/Library/Application\ Support/Code/User/settings.json.bak.$(date +%Y%m%d) 2>/dev/null || true
   ```

3. **Copy** this repo’s settings into the VS Code user folder:

   ```bash
   REPO="$HOME/path/to/vs-code-stuff"   # adjust after clone
   cp "$REPO/vscode/settings.json" \
      ~/Library/Application\ Support/Code/User/settings.json
   ```

4. Restart VS Code (**Cmd+Q**, then open again).

5. **Extensions** (optional). From the repo root:

   ```bash
   xargs -L1 "/Applications/Visual Studio Code.app/Contents/Resources/app/bin/code" --install-extension < vscode/extensions.txt
   ```

   If the `code` shell command is on your `PATH`, you can use `code --install-extension` instead.

## Windows / Linux

- **Windows** user `settings.json`: `%APPDATA%\Code\User\settings.json`
- **Linux** user `settings.json`: `~/.config/Code/User/settings.json`

Copy `vscode/settings.json` to the same relative location under that user folder.

## For another agent or future you

- The **entire theme** lives in `vscode/settings.json`; there is no separate color-theme extension.
- Prefer **Settings Sync** built into VS Code if you want ongoing sync instead of this repo.
- After changing the look locally, refresh the bundle by copying `settings.json` again and committing.

## License

Personal configuration; use however you like.
