# VSCode \(settings.json\)

```javascript
{
  /*** disabling vscode extra bloat stuff ***/
  "telemetry.enableTelemetry": false,
  "workbench.statusBar.feedback.visible": false,
  "editor.fontFamily": "Hasklig",
  "workbench.colorTheme": "Kimbie Dark",
  "editor.fontSize": 16,
  "editor.fontLigatures": true,
  "editor.multiCursorModifier": "ctrlCmd",
  "terminal.integrated.fontFamily": "Hasklig",
  "workbench.sideBar.location": "right",
  "editor.renderWhitespace": "none",
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.detectIndentation": true,
  "editor.wordWrap": "on",
  "editor.cursorBlinking": "smooth",
  "terminal.integrated.cursorStyle": "line",
  "editor.wordWrapColumn": 120,
  "editor.minimap.enabled": false,
  // fixing UI issues / no need to click confirm boxes
  "explorer.confirmDragAndDrop": false,
  "git.confirmSync": false,
  "git.autofetch": true,
  // no need to confirm imports when filename changes
  "javascript.updateImportsOnFileMove.enabled": "always",
  "javascript.implicitProjectConfig.experimentalDecorators": true, // stops errors using decorators
  // emmet and suggestions
  "editor.acceptSuggestionOnEnter": "off", // use tab for suggestions, so you can press enter to newline
  "editor.quickSuggestions": {
    "comments": false // no suggestions inside comments
  },
  "emmet.showSuggestionsAsSnippets": true,
  "emmet.triggerExpansionOnTab": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "HTML (Eex)": "html"
  },
  "emmet.syntaxProfiles": {
    "javascript": "jsx",
    "erb": "erb"
  },
  /*** general formatting ***/
  // toggle to false and enable [javascript] & [javascriptreact] when not using eslint
  "ruby.format": false,
  "ruby.codeCompletion": false,
  "solargraph.hover": true,
  "solargraph.completion": true,
  "solargraph.rename": false,
  "solargraph.diagnostics": true,
  //CSS
  // No unit for zero needed
  "css.lint.zeroUnits": "warning",
  "css.lint.idSelector": "warning",
  //SCSS
  // No unit for zero needed
  "scss.lint.zeroUnits": "warning",
  "scss.lint.idSelector": "warning",
  //intellisense plugin setting
  "path-intellisense.extensionOnImport": true,
  "path-intellisense.showHiddenFiles": true,
  "path-intellisense.autoSlashAfterDirectory": true,
  "workbench.colorCustomizations": {
    "tab.activeBackground": "#232833",
    "activityBar.background": "#282c34",
    "sideBar.background": "#282c34"
  },
  "window.zoomLevel": 0,
  // Allows to display errors.
  "scss.showErrors": false,
  // Add vendor prefixes to CSS when you save a file.
  "liveServer.settings.donotShowInfoMsg": true,
  "workbench.startupEditor": "newUntitledFile",
  "editor.tabCompletion": "on",
  "breadcrumbs.enabled": true,
  "sync.gist": "4f53f0100634a4ad5376ab6a49fe446a",
  "editor.suggestSelection": "first",
  "vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
  "code-runner.runInTerminal": true,
  "code-runner.saveFileBeforeRun": true,
  "code-runner.executorMap": {
    "cpp": "cd $dir && g++ -std=c++14 $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt"
  }
}
```

