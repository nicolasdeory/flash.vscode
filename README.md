# Flash VSCode

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Acknowledgements](#acknowledgements)

## Overview

**Flash VSCode** is a minimal port of the [flash.nvim](https://github.com/folke/flash.nvim) Neovim plugin, bringing fast, label-based code navigation to Visual Studio Code.

## Installation

1. Open Visual Studio Code.
2. Go to the Extensions view (`Ctrl+Shift+X` on Windows/Linux or `Cmd+Shift+X` on macOS).
3. Search for **Flash VSCode**.
4. Click **Install**.
5. Reload VS Code if prompted.

## Usage

1. **Activate Navigation:**
   Flash VSCode provides two main functionalities:
   - **`flash-vscode.start`**: Moves the cursor directly to the selected target.
   - **`flash-vscode.startSelection`**: Extends the selection from the original position to the target.

2. **Cancel Navigation:**
   - Press `Backspace` to remove the last character of your query, or press `Escape` to exit jump mode.

## Configuration

### Case Sensitivity

By default, `flash-vscode`'s search is case sensitive. To change this behavior, add to your settings:
```json
{
  "flash-vscode.caseSensitive": false
}
```

### VSCodeVim Integration

To invoke Flash VSCode commands from VSCodeVim, in your `settings.json`, add entries to `"vim.normalModeKeyBindingsNonRecursive"` as follows:

```json
"vim.normalModeKeyBindingsNonRecursive": [
  {
    "before": ["s"],
    "commands": ["flash-vscode.start"]
  },
  {
    "before": ["S"],
    "commands": ["flash-vscode.startSelection"]
  }, 
  {
    "before": [ "<BS>" ],
    "commands": [ "flash-vscode.backspace" ]
  },
]
```

This configuration triggers Flash VSCode when you press `s` or `S` in normal mode.

## Acknowledgements
* [flash.nvim](https://github.com/folke/flash.nvim) for the original ideas
* [Jumpy2](https://marketplace.visualstudio.com/items?itemName=DavidLGoldberg.jumpy2) for some of the implementation details