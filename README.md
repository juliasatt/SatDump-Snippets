# SatDump-Snippets

A collection of SatDump specific snippets using the VSCode snippet format.

## Usage

- If you're using [VSCode](https://code.visualstudio.com), you can take a look at [Create your own snippets](https://code.visualstudio.com/docs/editing/userdefinedsnippets#_create-your-own-snippets) for a in-depth explanation.
- If you're using [Neovim](https://neovim.io), you can use [LuaSnip](https://github.com/L3MON4D3/LuaSnip/tree/master) and follow their guide on [LuaSnip Docs](https://github.com/L3MON4D3/LuaSnip/blob/master/DOC.md#loaders).

- If you're using [NvChad](https://nvchad.com) like me, just take a look at the [NvChad Snippets Page](https://nvchad.com/docs/config/snippets)
- If you're using [LazyVim](https://www.lazyvim.org), see [LuaSnip Page](https://www.lazyvim.org/extras/coding/luasnip#luasnip-1)

> [!IMPORTANT]
> You need to have a `package.json` file at the root folder of the snippets.
> You can look at [Examples](#Examples) below or at the default [default](./vscode_snippets/package.json) file already in the repository.

## Default Snippets Format

By default the format being used is the VSCode one, more specifically [friendly-snippets](https://github.com/rafamadriz/friendly-snippets) (where you can find examples with the structure).

The files can be `*.json` or `*.jsonc`, however, using `*.json` is preferred as it's parser is faster, so unless you need comments, just go with `*.json`.

When specifying a language, you need to use the [language identifiers](https://code.visualstudio.com/docs/languages/identifiers) under `"language": [""]`, inside the `package.json` file.

## File Formatting

To format the file so it becomes more "organized", you can use something like [jsonls](https://github.com/microsoft/vscode-json-languageservice) (VSCode JSON language server).

## Examples

You can look inside the [cpp.json](./vscode_snippets/snippets/cpp/cpp.json) or the example below for a language specific snippet.

Example of `cpp.json` (`~/.config/snippets/cpp/cpp.json`)

```json
{
  "snippet-one": {
    "prefix": "snp1",
    "body": ["add_param_${1:simple}(p, \"$2\", \"$3\");"],
    "description": "SatDump's add parameter, defaults to simple, but can be overridden."
  }
}
```

Example of `package.json` (`~/.config/snippets/package.json`)

```json
{
  "name": "example-snippets",
  "contributes": {
    "snippets": [
      {
        "language": ["cpp", "c"],
        "path": "~/.config/snippets/cpp/cpp.json"
      }
    ]
  }
}
```
