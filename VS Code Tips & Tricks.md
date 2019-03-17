# Handy Tricks for VS Code

## Extensions

Useful extensions for everyday use.

[autoDocstring](https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring)

[Beautify](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify)

[Guides](https://marketplace.visualstudio.com/items?itemName=spywhere.guides)

[Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

[vscode-icons](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons)

[Charcoal Oceanic Next](https://marketplace.visualstudio.com/items?itemName=joshpeng.theme-charcoal-oceanicnext)

[Jupyter Notebook Previewer](https://marketplace.visualstudio.com/items?itemName=jithurjacob.nbpreviewer)

[Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)

[PlantUML](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml)


## Shortcuts

### Python Cell Symbol

Keyboard binding to add `#%%` to the in focus script.

```json
{
        "key": "ctrl+shift+a",
        "command": "type",
        "args": {"text": "#%%"},
        "when": "editorTextFocus"
    }
```