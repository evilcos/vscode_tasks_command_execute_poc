# just a test by slowmist

Arbitrary command execution on Open Folder via .vscode/tasks.json
- No Workspace Trust prompt: Cursor
- Workspace Trust prompt: VS Code, Antigravity, TRAE

## Triggering steps:
1. Download or clone this repository, then extract it if it’s a ZIP.
2. Launch Cursor / VS Code / Antigravity / TRAE and select File → Open Folder.
3. Choose the extracted folder.
4. Verify the PoC triggers: check the terminal output and note the Calculator launch. Reference screenshots: ./screenshot/.

PoC key: .vscode/tasks.json<br>
Detail: https://code.visualstudio.com/docs/debugtest/tasks

## Hardening steps (recommended):

- Press Ctrl + Shift + P (Mac: ⇧ Shift + ⌘ Command + P)
- Open User Settings → Features → Allow Automatic Tasks → set it to Off
- If Ctrl + Shift + P opens User Settings (JSON) directly, just set: task.allowAutomaticTasks: "off"

This works for Cursor / VS Code / Antigravity / TRAE and essentially any IDE built on VS Code.

If you’re using Cursor, you can also enable:
- Security → Workspace → Trust → Enabled

With this enabled, the first time you open a new folder you’ll get a Workspace Trust warning. And even if you choose to trust the workspace, commands hidden in .vscode/tasks.json will not auto-run anymore once Allow Automatic Tasks is turned off.

[@evilcos](https://x.com/evilcos/) [@SlowMist_Team](https://x.com/SlowMist_Team)


