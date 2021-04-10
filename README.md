| [chinese][chinese-link] | [english][english-link] |
|-------------------------|-------------------------|

[english-link]: https://github.com/kay54068/athena-language-support/blob/master/README_EN.md "english README"
[chinese-link]: https://github.com/kay54068/athena-language-support/blob/master/README.md "中文 README"
# Visual Studio Code Athena language support

This extension provides rAthena-flavored Athena language syntax highlighting and code snippets.

## File extension support

Athena Language Support automatically highlights files with .rascript extension.


## 安裝方式

1. 進入 `C:\Users\{用户名}\.vscode\extensions` 目錄
2. 下載此專案
```
git clone https://github.com/kay54068/athena-language-support.git
```
3. 重新開啟 VS Code / reload window
   - reload window:  
     Ctrl + Shift + P -> reload window


## VS Code 設定

1. VS code 右下角的 選擇語言模式需選擇 `athena`
2. 由於此pulgin 有自定義 syntaxes hightlight , 所以需要設定 'editor.tokenColorCustomizations' config
3. "editor.snippetSuggestions": "top" 設定可讓 自定義的 snippet 優先可以選擇.

Ctrl + Shift + P -> Setting -> select "開啟設定(JSON)" -> 新增以下項目:

```json
    "editor.snippetSuggestions": "top",
    "editor.tokenColorCustomizations": {
      "textMateRules": [
        // character
        {
          // temporary
          "scope": ["variable.temporal.character"],
          "settings": {
            "foreground": "#fff566",
            "fontStyle": "bold"
          }
        },    
        // global
        {
          "scope": ["variable.global"],
          "settings": {
            "foreground": "#b4a411",
            "fontStyle": "bold"
          }
        },
        {
        // temporary
          "scope": ["variable.temporal.global"],
          "settings": {
            "foreground": "#6669ff",
            "fontStyle": "bold"
          }
        },
        // NPC
        {
          "scope": ["variable.npc"],
          "settings": {
            "foreground": "#e74f21",
            "fontStyle": "bold"
          }
        },
        // Scope
        {
          "scope": ["variable.scope"],
          "settings": {
            "foreground": "#ff66ff",
            "fontStyle": "bold"
          }
        },
        // permanent local
        {
          "scope": ["variable.instance"],
          "settings": {
            "foreground": "#cc66ff",
            "fontStyle": "bold"
          }
        },
        // permanent local
        {
          "scope": ["variable.permanent"],
          "settings": {
            "foreground": "#0caa2e",
            "fontStyle": "bold"
          }
        },
        // permanent global
        {
          "scope": ["variable.permanent.global"],
          "settings": {
            "foreground": "#66ffc4",
            "fontStyle": "bold"
          }
        }
      ]
    }
```
3. 重載視窗
    Ctrl + Shift + P -> reload window

## 支援 Snippets 清單


* `defnpc`, `defnpcfloat`, `defwarp`, and `defshop` (In-game objects definition)
* `deffunction` (Function definition)
* `On:` event handler snippet
* `for`, `while`, `do` flow control snippet
* `mes "<string>"{,"<string>"{,...}};`
  - script_msg_base : 單行 message
  - script_msg_mutiline : 多行 message
  - script_msg_color :  message 文字帶有顏色