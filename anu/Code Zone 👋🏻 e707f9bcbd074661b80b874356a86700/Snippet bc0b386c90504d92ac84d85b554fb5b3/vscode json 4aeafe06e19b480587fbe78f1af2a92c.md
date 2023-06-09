# vscode json

Status Learn: Not started
type: vscode

```php
{
    "terminal.integrated.defaultProfile.windows": "Git Bash",
    "make.configureOnOpen": true,
    "security.workspace.trust.banner": "never",
    "editor.fontFamily": "dank mono",
    "editor.fontLigatures": true,
    "editor.suggestSelection": "first",
    "vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
    "explorer.confirmDelete": false,
    "files.exclude": {
        "**/.classpath": true,
        "**/.project": true,
        "**/.settings": true,
        "**/.factorypath": true
    },
    "[dart]": {
        "editor.formatOnSave": true,
        "editor.formatOnType": true,
        "editor.rulers": [
            80
        ],
        "editor.selectionHighlight": false,
        "editor.suggest.snippetsPreventQuickSuggestions": false,
        "editor.suggestSelection": "first",
        "editor.tabCompletion": "onlySnippets",
        "editor.wordBasedSuggestions": false
    },
    // "C_Cpp.updateChannel": "Insiders",
    "terminal.integrated.ignoreProcessNames": [
        "zsh",
        "bash",
        "starship",
        "oh-my-posh"
    ],
    "dart.previewFlutterUiGuidesCustomTracking": true,
    "dart.previewFlutterUiGuides": true,
    "[cpp]": {
        "editor.defaultFormatter": "ms-vscode.cpptools"
    },
    "editor.formatOnSave": true,
    "C_Cpp.errorSquiggles": "Enabled",
    "terminal.integrated.cursorStyle": "line",
    "terminal.integrated.cursorBlinking": true,
    "codesnap.boxShadow": "rgba(0, 0, 0, 0.55) 5px 5px 20px",
    "codesnap.showLineNumbers": false,
    // bash
    "terminal.integrated.profiles.windows": {
        "Git-Bash": {
            "path": "D:\\Program Files\\Git\\bin\\bash.exe",
        }
    },
    "maven.showInExplorerContextMenu": true,
    "editor.renderLineHighlight": "none",
    "editor.matchBrackets": "never",
    "editor.scrollbar.verticalScrollbarSize": 5,
    "editor.occurrencesHighlight": false,
    "bracketPairColorizer.depreciation-notice": false,
    "code-runner.showRunIconInEditorTitleMenu": false,
    "terminal.integrated.tabs.showActiveTerminal": "never",
    "workbench.iconTheme": "material-icon-theme",
    "window.titleSeparator": " -",
    "workbench.startupEditor": "none",
    //punya gw
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
    "terminal.external.windowsExec": "C:\\Users\\Sahabat\\AppData\\Local\\Microsoft\\WindowsApps\\wt.exe",
    "doki.background.enabled": false,
    // "doki.wallpaper.path": "F:/Desain Grafis/@pojan/rect829.png",
    "doki.sticker.path": "F:/Desain Grafis/@pojan/vscode/donkey-butter.gif",
    // "workbench.experimental.layoutControl.type": "toggles",
    "workbench.layoutControl.type": "menu",
    "editor.scrollbar.horizontalScrollbarSize": 5,
    "editor.cursorBlinking": "smooth",
    "liveServer.settings.donotShowInfoMsg": true,
    "terminal.integrated.gpuAcceleration": "off",
    "tabnine.experimentalAutoImports": true,
    "window.title": "${folderName} | ${activeEditorShort} 🔥",
    // https://dev.to/js2me/make-your-own-custom-theme-for-vs-code-me7
    // "vscode_custom_css.imports": [
    //     "file:///C:/Users/sahabat/vscode_css/vscodeStyle.css"
    // ],
    "code-runner.executorMap": {
        "cpp": "g++ $fullFileName -o $fileNameWithoutExt.exe && start $fileNameWithoutExt.exe"
    },
    "workbench.editor.showTabs": true,
    "workbench.editor.tabSizing": "shrink",
    "security.workspace.trust.untrustedFiles": "open",
    "workbench.colorTheme": "Material Theme",
    "workbench.colorCustomizations": {
        "editorError.background": "#ff00001c",
        "editorError.foreground": "#ff000000",
        "editorError.border": "#ff0000",
        // "editor.rangeHighlightBackground": "#7f997f",
        // "editorGroupHeader.tabsBackground": "#00000000"
        "editorGutter.background": "#0000",
        // "editorGroupHeader.tabsBackground": "#00000000",
        // "editorGroupHeader.border": "#00000000",
        // "editor.background": "#00000000",
        // "foreground": "#ff0000"
        // "sideBar.background": "#00000000",
        // "sideBar.foreground":
        // "statusBar.background": "#ff0000",
        // "statusBar.foreground": "#ff0000",
        // "statusBar.noFolderBackground": "#ff0000",
        // "statusBar.noFolderForeground": "#fa0404"
    },
    "c-cpp-compile-run.run-in-external-terminal": true,
    "editor.codeLensFontFamily": " 'Dank Mono'",
    "editor.fontWeight": "normal",
    "screencastMode.fontSize": 20,
    "screencastMode.verticalOffset": 5,
    "workbench.productIconTheme": "fluent-icons",
    "breadcrumbs.enabled": false,
    "database-client.showQuery": true,
    "editor.renderWhitespace": "none",
    "editor.mouseWheelZoom": true,
    "screencastMode.keyboardOverlayTimeout": 2000,
    "editor.guides.indentation": false,
    "editor.lineHeight": 3,
    "editor.wordWrap": "on",
    "terminal.integrated.fontFamily": "'MesloLGS NF'",
    "git.autofetch": true,
    "git.confirmSync": false,
    "codesnap.backgroundColor": "rgba(0, 0, 0, 0)",
    "codesnap.realLineNumbers": true,
    "editor.cursorSmoothCaretAnimation": true,
    "editor.smoothScrolling": true,
    "customizeUI.font.monospace": "fira code",
    "customizeUI.font.regular": "inter",
    "window.titleBarStyle": "custom",
    "editor.minimap.enabled": false,
    "editor.suggest.showStatusBar": true,
    "workbench.layoutControl.enabled": false,
    "window.menuBarVisibility": "toggle",
    "explorer.confirmDragAndDrop": false,
    "files.autoSave": "afterDelay",
    "git.enableSmartCommit": true,
    "VSCodeNotion.accessToken": "secret_MaEUEhv2Lq92lR5tKiohxVckrmATxcvh3zvg4gVgFHj",
    "VSCodeNotion.allowEmbeds": true,
    "markdown.extension.preview.autoShowPreviewToSide": true,
    "markdown.extension.print.onFileSave": true,
    "workbench.statusBar.visible": false,
    "window.zoomLevel": 1,
    "workbench.activityBar.visible": false
}
```