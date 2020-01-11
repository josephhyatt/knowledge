# settings.json/snippets \(VSCode\)

## settings.json

```bash
{
    /******************************************/
    /*** Disabling VSCode Extra Bloat Stuff ***/
    /******************************************/
    "telemetry.enableTelemetry": false,
    "workbench.statusBar.feedback.visible": false,
    "editor.fontFamily": "Fira Code",
    "workbench.colorTheme": "Kimbie Dark",
    "editor.fontSize": 17,
    "editor.fontLigatures": true,
    "editor.multiCursorModifier": "ctrlCmd",
    "terminal.integrated.fontFamily": "Fira Code",
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
    "editor.snippetSuggestions": "top",
    "explorer.confirmDragAndDrop": false, // Fixing UI issues / no need to click confirm boxes
    "git.confirmSync": false,
    "git.autofetch": true,
    "javascript.updateImportsOnFileMove.enabled": "always", // No need to confirm imports when filename changes
    "javascript.implicitProjectConfig.experimentalDecorators": true, // Stops errors using decorators
    "editor.acceptSuggestionOnEnter": "off", // Use TAB for suggestions, so you can press enter to newline
    "editor.quickSuggestions": {
      "comments": false // No suggestions inside comments
    },
    "emmet.showSuggestionsAsSnippets": true,
    "emmet.triggerExpansionOnTab": true,
    "emmet.syntaxProfiles": {
      "javascript": "jsx",
      "erb": "erb"
    },
    /******************************************/
    /********** General Formatting ************/
    /******************************************/
    "ruby.format": false, // toggle to false and enable [javascript] & [javascriptreact] when not using eslint
    "ruby.codeCompletion": false,
    "solargraph.hover": true,
    "solargraph.completion": true,
    "solargraph.rename": false,
    "solargraph.diagnostics": true,
    /******************************************/
    /*************** CSS **********************/
    /******************************************/
    "css.lint.zeroUnits": "warning", // No unit for zero needed
    "css.lint.idSelector": "warning",
    /******************************************/
    /*************** SCSS *********************/
    /******************************************/
    "scss.lint.zeroUnits": "warning", // No unit for zero needed
    "scss.lint.idSelector": "warning",
    "path-intellisense.extensionOnImport": true, // Intellisense plugin setting
    "path-intellisense.showHiddenFiles": true,
    "path-intellisense.autoSlashAfterDirectory": true,
    "workbench.colorCustomizations": {
      "tab.activeBackground": "#232833",
      "activityBar.background": "#282c34",
      "sideBar.background": "#282c34"
    },
    "window.zoomLevel": 0,
    "scss.showErrors": false, // Allows to display errors.
    "liveServer.settings.donotShowInfoMsg": true, // Add vendor prefixes to CSS when you save a file.
    "workbench.startupEditor": "newUntitledFile",
    "editor.tabCompletion": "on",
    "breadcrumbs.enabled": true,
    "editor.suggestSelection": "first",
    "vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
    "code-runner.runInTerminal": true,
    "code-runner.saveFileBeforeRun": true,
    /******************************************/
    /************** C++ ***********************/
    /******************************************/
    "code-runner.executorMap": {
      "cpp": "cd $dir && g++ -std=c++14 $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt"
    },
    "C_Cpp.default.cppStandard": "c++14",
    "C_Cpp.default.cStandard": "c11",
    "C_Cpp.updateChannel": "Insiders",
    "workbench.iconTheme": "vscode-icons",
    "python.jediEnabled": false,
    /******************************************/
    /************** Files *********************/
    /******************************************/
    "search.exclude": {
      "**/.git": true,
      "**/node_modules": true,
      "**/bower_components": true,
      "**/tmp": true,
      "**/coverage": true,
      "**/log": true,
      "**/public/uploads": true
    },
    "files.exclude": {
      "**/.git": true,
      "**/.svn": true,
      "**/.hg": true,
      "**/CVS": true,
      "**/.DS_Store": true,
      "**/log": true
    },
    "files.associations": {
      "*.html": "html"
    },
    /******************************************/
    /*********** Format On Save ***************/
    /******************************************/
    "editor.formatOnSave": false, // <-------- FORMAT ON SAVE <-------------------
    "search.location": "panel",
    "files.trimTrailingWhitespace": true,
    "liveServer.settings.donotVerifyTags": true,
    "editor.renderIndentGuides": false,
    "python.formatting.provider": "black",
    /******************************************/
    /********** Custom Font Colors ************/
    /******************************************/
    /*********** ctrl + shift + p *************/
    /****** Developer: Inspect TM Scopes ******/
    "editor.tokenColorCustomizations": {
      "textMateRules": [
        {
          "scope": [
            "storage"
          ],
          "settings": {
            "foreground": "#cb91dd"
          }
        },
        {
          "scope": [
            "keyword.control"
          ],
          "settings": {
            "foreground": "#da9e1f"
          }
        },
        {
          "scope": [
            "keyword"
          ],
          "settings": {
            "foreground": "#c1d164bd"
          }
        },
        {
          "scope": [
            "support.function"
          ],
          "settings": {
            "foreground": "#3de2ff88"
          }
        },
        {
          "scope": [
            "string"
          ],
          "settings": {
            "foreground": "#cbe45b9c"
          }
        },
        {
          "scope": [
            "entity"
          ],
          "settings": {
            "foreground": "#ffffff9c"
          }
        },
        {
          "scope": [
            "keyword.operator"
          ],
          "settings": {
            "foreground": "#3091b8bd"
          }
        },
        {
          "scope": [
            "constant"
          ],
          "settings": {
            "foreground": "#d1842b"
          }
        },
        {
          "scope": [
            "variable"
          ],
          "settings": {
            "foreground": "#7db170"
          }
        },
        {
          "scope": [
            "entity.name.type"
          ],
          "settings": {
            "foreground": "#cacaca"
          }
        },
        {
          "scope": [
            "keyword.other.using"
          ],
          "settings": {
            "foreground": "#c7c68b"
          }
        },
        {
          "scope": [
            "entity.name.tag"
          ],
          "settings": {
            "foreground": "#b38117"
          }
        },
        {
          "scope": [
            "entity.other.attribute-name"
          ],
          "settings": {
            "foreground": "#7c8596"
          }
        },
        {
          "scope": [
            "entity.name.function"
          ],
          "settings": {
            "foreground": "#c46c6c"
          }
        },
        /** Text Color **/
        // HTML Text
        {
          "scope": [
            "text.html.jinja"
          ],
          "settings": {
            "foreground": "#93a192"
          }
        },
        // Python Text
        {
          "scope": [
            "source.python"
          ],
          "settings": {
            "foreground": "#bec4b3"
          }
        },
        {
          "scope": [
            "variable.parameter.function"
          ],
          "settings": {
            "foreground": "#cc6a6a"
          }
        },
        // Shell Text
        {
          "scope": [
            "source.shell"
          ],
          "settings": {
            "foreground": "#cfd6c1"
          }
        },
        // Comment Text
        {
          "scope": [
            "comment"
          ],
          "settings": {
            "foreground": "#7e602c"
          }
        },
        // Hashtage Text
        {
          "scope": [
            "punctuation.definition.comment"
          ],
          "settings": {
            "foreground": "#7e602c"
          }
        }
      ]
    },
    "explorer.confirmDelete": false,
    "sync.gist": "d27ef29f5aa3c5dd6c54cba0fc67cdbe",
    "cSpell.userWords": [
      "pyautogui"
    ],
    "python.pythonPath": "/home/jh/anaconda3/bin/python",
    "terminal.integrated.inheritEnv": false
  }
```

