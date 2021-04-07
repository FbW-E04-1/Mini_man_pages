# Snippets for Visual Studio Code

A "snippet" is a piece of code that you need to use often, that you can insert automatically by typing a "trigger", then pressing the `Tab` key. Using snippets can save you a lot of time.

[Further reading](https://code.visualstudio.com/docs/editor/userdefinedsnippets)

## Share your Snippets

Each time you create a snippet that you are proud of (see below), you can add it to the appropriate file on this Wiki:

* [HTML snippets](html.json.md)
* [CSS snippets](css.json.md)
* [JavaScript snippets](javascript.json.md)

You can also check these files to see if someone else has already created a snippet that will save _you_ time.

## Create Your Own
Any time you find yourself retyping the same code, you can create your own snippets. For example, if you create a file at
`~/.config/Code/User/snippets/javascript.json` and add the following lines...

```json
 {
   "clog": {
        "prefix": "clog",
        "body": "console.log(\"${1:data}:\", ${1:data})",
        "description": "Create a console.log command for a given variable",
        "scope": "source.js"
    }
}
```

... in any file with the extension `.js`, you will be able to type `clog` then `tab`, to make the following text appear:

```javascript
console.log("data:", data)
```

The two occurences of the word "data" will be selected, so you can type your own variable name without moving your mouse.

[Further reading](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_create-your-own-snippets)

## Keyboard Triggers for Snippets

To continue the example above: suppose you want to log a second variable: `info`. You might want your `console.log()` command to look like this:

```javascript
console.log("data:", data, "info:", info)
```

You can add a second snippet to your javascript.json file:

```json
,
    "param": {
        "prefix": "param",
        "body": "\"$SELECTION:\", $SELECTION",
        "description": "For adding a labeled variable to a console.log() statement",
        "scope": "source.js"
    }
```
Notice that this snippet includes the string `$SELECTION`, in two places. This will take whatever text you have currently selected, wrap it in `"` double quote marks, add a comma and then repeat the selected text. But you can't type `param` and then press the `tab` without replacing the selected text.

The solution is to add a keyboard shortcut. Open the file at `~/.config/Code/User/keybindings.json`, and add the following just before the closing `}` line:

```json
  ,
  {
    "key": "ctrl+shift+p",
    "command": "editor.action.insertSnippet",
    "args": { "name": "param" }
  }
```
After you save the file, pressing Ctrl-Shift-P will trigger the `param` snippet.

You can now add the word "info" to the existing command, like this...

```javascript
console.log("data:", data, info)
```

... and then select the word "info" and press `Ctrl-Shift-P`. This should be the result:


```javascript
console.log("data:", data, "info:", info)
```

[Further reading](https://code.visualstudio.com/updates/v1_9#_insert-snippets)
