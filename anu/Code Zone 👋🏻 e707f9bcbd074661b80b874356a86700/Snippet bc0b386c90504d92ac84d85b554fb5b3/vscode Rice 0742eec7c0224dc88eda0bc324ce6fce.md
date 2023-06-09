# vscode Rice

Status Learn: Not started
type: vscode

<aside>
🥎 basic json

</aside>

```json
{
    "terminal.integrated.defaultProfile.windows": "Git Bash",
    "security.workspace.trust.banner": "never",
    "editor.fontFamily": "jetbrains mono,dank mono,cascadia code,MesloLGS NF,",
    "editor.fontLigatures": true,
    "editor.suggestSelection": "first",
    "explorer.confirmDelete": false,
    "editor.formatOnSave": true,
    "terminal.integrated.cursorStyle": "line",
    "terminal.integrated.cursorBlinking": true,
    "editor.renderLineHighlight": "none",
    "editor.matchBrackets": "never",
    "editor.scrollbar.verticalScrollbarSize": 5,
    "editor.occurrencesHighlight": false,
    "terminal.integrated.tabs.showActiveTerminal": "never",
    "workbench.iconTheme": "material-icon-theme",
    "window.titleSeparator": " -",
    "workbench.startupEditor": "none",
    //punya gw
    "terminal.external.windowsExec": "C:\\Users\\Sahabat\\AppData\\Local\\Microsoft\\WindowsApps\\wt.exe",
    "workbench.layoutControl.type": "menu",
    "editor.scrollbar.horizontalScrollbarSize": 5,
    "editor.cursorBlinking": "smooth",
    "terminal.integrated.gpuAcceleration": "off",
    "window.title": "📁 ${folderName} ~ ${activeEditorShort} ",
    "workbench.editor.showTabs": true,
    "workbench.editor.tabSizing": "shrink",
    "security.workspace.trust.untrustedFiles": "open",
    "workbench.colorTheme": "Aurora X",
    "editor.codeLensFontFamily": " 'Dank Mono'",
    "editor.fontWeight": "normal",
    "screencastMode.fontSize": 20,
    "screencastMode.verticalOffset": 5,
    "breadcrumbs.enabled": false,
    "editor.renderWhitespace": "none",
    "editor.mouseWheelZoom": true,
    "screencastMode.keyboardOverlayTimeout": 2000,
    "editor.guides.indentation": false,
    "editor.lineHeight": 2,
    "editor.wordWrap": "on",
    "terminal.integrated.fontFamily": "'MesloLGS NF'",
    "git.autofetch": true,
    "git.confirmSync": false,
    "editor.cursorSmoothCaretAnimation": true,
    "editor.smoothScrolling": true,
    "window.titleBarStyle": "custom",
    "editor.minimap.enabled": false,
    "editor.suggest.showStatusBar": true,
    "workbench.layoutControl.enabled": false,
    "explorer.confirmDragAndDrop": false,
    "files.autoSave": "afterDelay",
    "git.enableSmartCommit": true,
    "workbench.statusBar.visible": false,
    "window.zoomLevel": 1.5,
    "window.menuBarVisibility": "toggle",
    "workbench.activityBar.visible": false
}
```

<aside>
🥎 text italic

</aside>

```json
"editor.tokenColorCustomizations": {
        "textMateRules": [
            {
                "scope": [
                    //following will be in italic (=FlottFlott)
                    "comment",
                    "entity.name.tag.html",
                    "entity.name.type.class", //class names
                    "keyword", //import, export, return…
                    // "constant", //String, Number, Boolean…, this, super
                    // "storage.modifier", //static keyword
                    "storage.type", //class keyword
                    // "entity.other.attribute-name",
                    "entity.other.attribute-name",
                    "entity.name.type.cpp",
                    "entity.name.tag",
                ],
                "settings": {
                    "fontStyle": " ",
                }
            },
            {
                "scope": [
                    "keyword.operator", //import, export, return…
                    // "variable"
                ],
                "settings": {
                    "fontStyle": "bold"
                }
            },
            {
                "scope": [
                    "support.constant",
                ],
                "settings": {
                    "fontStyle": ""
                }
            }
        ]
    },
```