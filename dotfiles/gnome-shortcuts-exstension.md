# shortcuts.json

This is my **custom** `shortcuts.json` for the Shortcuts GNOME extension.&#x20;

```bash
{
	/******************************************/
	/*** Disabling VSCode Extra Bloat Stuff ***/
	/******************************************/
	"telemetry.enableTelemetry": false,
	"editor.fontFamily": "Fira Code",
	"editor.fontSize": 15,
	"editor.fontLigatures": true,
	"editor.multiCursorModifier": "ctrlCmd",
	"window.title": "${activeEditorMedium}${separator}${rootName}",
	"terminal.integrated.fontFamily": "FiraCode Nerd Font",
	"workbench.sideBar.location": "right",
	"editor.renderWhitespace": "none",
	"editor.insertSpaces": true,
	"editor.detectIndentation": false,
	"editor.wordWrap": "wordWrapColumn",
	"editor.wordWrapColumn": 160,
	"editor.cursorBlinking": "smooth",
	"terminal.integrated.cursorStyle": "line",
	"editor.minimap.enabled": false,
	"editor.snippetSuggestions": "top",
	"editor.letterSpacing": 0.2,
	"explorer.confirmDragAndDrop": false, // Fixing UI issues / no need to click confirm boxes
	"git.confirmSync": false,
	"git.autofetch": true,
	"python.formatting.blackPath": "C:\\Users\\josep\\AppData\\Roaming\\Python\\Python39\\Scripts\\black",
	"javascript.updateImportsOnFileMove.enabled": "always", // No need to confirm imports when filename changes
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
	"python.sortImports.args": ["--src=${workspaceFolder}"],
	/******************************************/
	/*************** Django *******************/
	/******************************************/
	"files.associations": {
		"**/templates/*.html": "django-html",
		"**/templates/*": "django-txt",
		"**/requirements{/**,*}.{txt,in}": "pip-requirements",
		"*.html": "html"
	},
	"emmet.includeLanguages": {
		"django-html": "html",
		"javascript": "javascriptreact"
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
	// "workbench.colorCustomizations": {
	// 	"tab.activeBackground": "#232833",
	// 	"activityBar.background": "#282c34",
	// 	"sideBar.background": "#282c34",
	// 	"editor.background": "#282c34",
	// 	"terminal.background": "#282c34"
	// },
	"window.zoomLevel": 1,
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
	"python.jediEnabled": false,
	/******************************************/
	/************** Files *********************/
	/******************************************/
	"search.exclude": {
		"**/.git": true,
		"**/node_modules": true,
		"**/bower_components": true,
		// "**/tmp": true,
		"**/coverage": true
		// "**/log": true,
		// "**/public/uploads": true
	},
	"files.exclude": {
		"**/.git": true,
		"**/.svn": true,
		"**/.hg": true,
		"**/CVS": true,
		"**/.DS_Store": true,
		"**/log": true
	},
	/******************************************/
	/*********** Format On Save ***************/
	/******************************************/
	"workbench.iconTheme": "material-icon-theme",
	"editor.defaultFormatter": "esbenp.prettier-vscode",
	"editor.formatOnSave": true,
	"[python]": {
		"editor.formatOnSave": true,
		"editor.defaultFormatter": "ms-python.python"
	},
	"[javascript]": {
		"editor.formatOnSave": true,
		"editor.defaultFormatter": "esbenp.prettier-vscode"
	},
	"editor.codeActionsOnSave": {
		"source.organizeImports": true
	},
	"python.formatting.provider": "black",
	"terminal.integrated.shell.windows": "C:\\Windows\\System32\\WindowsPowerShell\\v1.0\\powershell.exe",
	"files.trimTrailingWhitespace": true,
	"liveServer.settings.donotVerifyTags": true,
	"editor.renderIndentGuides": false,
	/******************************************/
	/********** Custom Font Colors ************/
	/******************************************/
	/*********** ctrl + shift + p *************/
	/****** Developer: Inspect TM Scopes ******/
	"editor.tokenColorCustomizations": {
		"textMateRules": [
			{
				"scope": ["entity.other.django.delimiter.tag"],
				"settings": {
					"foreground": "#8EC07C"
				}
			},
			{
				"scope": ["variable.other.django"],
				"settings": {
					"foreground": "#B77788"
				}
			},
			{
				"scope": ["entity.name.tag.html"],
				"settings": {
					"foreground": "#83A598"
				}
			},
			{
				"scope": ["entity.other.attribute-name.html"],
				"settings": {
					"foreground": "#F8BB2F"
				}
			},
			{
				"scope": ["string.quoted.double.html"],
				"settings": {
					"foreground": "#B8BB26"
				}
			},
			{
				"scope": ["punctuation.definition.tag.begin.html"],
				"settings": {
					"foreground": "#83A598"
				}
			},
			{
				"scope": ["punctuation.definition.tag.end.html"],
				"settings": {
					"foreground": "#83A598"
				}
			},
			{
				"scope": ["support.type.property-name.json"],
				"settings": {
					"foreground": "#83A598"
				}
			},
			{
				"scope": ["variable.other.property.js"],
				"settings": {
					"foreground": "#8f9a95"
				}
			},
			{
				"scope": ["variable.other.object.property"],
				"settings": {
					"foreground": "#b34040"
				}
			},
			{
				"scope": ["entity.name.tag.js"],
				"settings": {
					"foreground": "#83A598"
				}
			},
			{
				"scope": ["entity.other.attribute-name.js"],
				"settings": {
					"foreground": "#B8BB26"
				}
			},
			{
				"scope": ["string.quoted.double.js"],
				"settings": {
					"foreground": "#c1c1b3"
				}
			}
		]
	},
	"workbench.colorCustomizations": {
		"tab.activeBackground": "#557e4696",
		"tab.border": "#949353",
		"tab.inactiveBackground": "#1D2021",
		"terminal.background": "#1D2021",
		"terminal.foreground": "#A89984",
		// "sideBar.background": "#1d20212d",
		"sideBar.foreground": "#A89984",
		"panel.background": "#1d20212d"
	},
	"editor.mouseWheelZoom": true,
	"workbench.settings.useSplitJSON": true,
	"workbench.editor.highlightModifiedTabs": true,
	"files.trimFinalNewlines": true,
	"explorer.confirmDelete": false,
	"sync.gist": "d27ef29f5aa3c5dd6c54cba0fc67cdbe",
	"cSpell.userWords": ["pyautogui"],
	"terminal.integrated.inheritEnv": false,
	"terminal.integrated.shell.linux": "/bin/zsh",
	"terminal.integrated.windowsEnableConpty": false,
	"kite.showWelcomeNotificationOnStartup": false,
	"python.languageServer": "Pylance",
	"files.autoSave": "afterDelay",
	"python.defaultInterpreterPath": "/sbin/python",
	"verilog.linting.linter": "iverilog",
	"mssql.connections": [
		{
			"server": "{{put-server-name-here}}",
			"database": "{{put-database-name-here}}",
			"user": "{{put-username-here}}",
			"password": "{{put-password-here}}"
		}
	],
	"prettier.useTabs": true,
	"workbench.editorAssociations": {
		"*.ipynb": "jupyter-notebook"
	},
	"workbench.colorTheme": "Gruvbox Material Dark",
	"notebook.cellToolbarLocation": {
		"default": "right",
		"jupyter-notebook": "left"
	},
	"editor.inlineSuggest.enabled": true,
	"tabnine.experimentalAutoImports": true,
	"explorer.openEditors.sortOrder": "alphabetical",
	"github.copilot.enable": {
		"*": true,
		"yaml": false,
		"plaintext": true,
		"markdown": true
	},
	"terminal.integrated.defaultProfile.windows": "Ubuntu (WSL)",
	"redhat.telemetry.enabled": false,
	"xml.symbols.maxItemsComputed": 50000
}

```
