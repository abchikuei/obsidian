## ✍️ VSCode Configuration

---

### ⚙️ **Code Snippets**

```json
{
  "Fast Console Log": {
    "scope": "typescript",
    "prefix": "cl",
    "body": "console.log($0);"
  },
  "Debug log": {
    "scope": "typescript",
    "prefix": "cd",
    "body": "console.debug('$1:', $1);"
  },
  "Swapper": {
    "scope": "typescript",
    "prefix": "swap",
    "body": "[$1[$2],$1[$3]] = [$1[$3], $1[$2]];"
  },
  "Math.max": {
    "scope": "typescript",
    "prefix": "max",
    "body": "Math.max($0)"
  },
  "Math.min": {
    "scope": "typescript",
    "prefix": "min",
    "body": "Math.min($0)"
  },
  "Math.abs": {
    "scope": "typescript",
    "prefix": "mod",
    "body": "Math.abs($1)"
  },
  "Math.floor": {
    "scope": "typescript",
    "prefix": "floor",
    "body": "Math.floor($1)"
  },
  "Math.ceil": {
    "scope": "typescript",
    "prefix": "ceil",
    "body": "Math.ceil($1)"
  },
  "Math.random": {
    "scope": "typescript",
    "prefix": "rand",
    "body": "Math.random()"
  },
  "Convert to Number": {
    "scope": "typescript",
    "prefix": "int",
    "body": "Number($1)"
  },
  "Convert to String": {
    "scope": "typescript",
    "prefix": "str",
    "body": "String($1)"
  },
  "Convert to Boolean": {
    "scope": "typescript",
    "prefix": "bool",
    "body": "Boolean($1)"
  }
}
```

---

### ✏️ **Type Snippets**

```json
{
  "Set type number": {
    "scope": "typescript",
    "prefix": "n",
    "body": "number"
  },
  "Set type number[]": {
    "scope": "typescript",
    "prefix": "nn",
    "body": "number[]"
  },
  "Set type number[][]": {
    "scope": "typescript",
    "prefix": "nnn",
    "body": "number[][]"
  },
  "Set type string": {
    "scope": "typescript",
    "prefix": "s",
    "body": "string"
  },
  "Set type string[]": {
    "scope": "typescript",
    "prefix": "ss",
    "body": "string[]"
  },
  "Set type string[][]": {
    "scope": "typescript",
    "prefix": "sss",
    "body": "string[][]"
  },
  "Set type boolean": {
    "scope": "typescript",
    "prefix": "b",
    "body": "boolean"
  },
  "Set type boolean[]": {
    "scope": "typescript",
    "prefix": "bb",
    "body": "boolean[]"
  },
  "Set type boolean[][]": {
    "scope": "typescript",
    "prefix": "bbb",
    "body": "boolean[][]"
  }
}
```

---

### 🏆 **CP Snippets**

```json
{
    "Codeforces": {
        "prefix": "lf",
        "body": [
            "import * as fs from \"fs\";",
            "",
            "const readInput = () => {",
            "    const debug = process.env.DEBUG_FILE_INPUT;",
            "    return fs.readFileSync(debug ?? 0, \"utf-8\");",
            "};",
            "",
            "const data = readInput();",
            "const tokens = data.split(/\\s+/g).filter(Boolean);",
            "const lines = data.split(/\\r?\\n/);",
            "",
            "let t = 0;",
            "let l = 0;",
            "",
            "const read = () => tokens[t++]",
            "const int = () => Number(read())",
            "const line = () => lines[l++]",
            "const readline = () => line().trim().split(/\\s+/g)",
            "",
            "let out = '';",
            "const write = (...s: any[]) => (out += s.join(' ') + \"\\n\");",
            "const flush = () => process.stdout.write(out);",
            "",
            "function solve() {",
            "    $0",
            "}",
            "",
            "function main() {",
            "    solve();",
            "    flush();",
            "}",
            "",
            "main();"
        ]
    },
    "Neetcode": {
        "prefix": "nc",
        "body": [
            "export class Solution {",
            "    $1 ($2) {",
            "        $0",
            "    }",
            "}"
        ]
    },
    "Leetcode": {
        "prefix": "lc",
        "body": [
            "export function $1 ($2) {",
            "   $0",
            "}"
        ]
    }
}
```

### ⚙️ **General Keybindings**

```json
[
  {
    "key": "cmd+shift+a",
    "command": "workbench.action.tasks.runTask",
    "args": "submit"
  },
  {
    "key": "cmd+shift+z",
    "command": "workbench.action.tasks.runTask",
    "args": "run"
  },
  {
    "key": "cmd+shift+j",
    "command": "workbench.files.action.collapseExplorerFolders"
  },
  { "key": "cmd+1", "command": "workbench.action.openEditorAtIndex1" },
  { "key": "cmd+2", "command": "workbench.action.openEditorAtIndex2" },
  { "key": "cmd+3", "command": "workbench.action.openEditorAtIndex3" },
  { "key": "cmd+4", "command": "workbench.action.openEditorAtIndex4" },
  { "key": "cmd+5", "command": "workbench.action.openEditorAtIndex5" },
  { "key": "cmd+6", "command": "workbench.action.openEditorAtIndex6" },
  { "key": "cmd+7", "command": "workbench.action.openEditorAtIndex7" },
  { "key": "cmd+8", "command": "workbench.action.openEditorAtIndex8" },
  { "key": "cmd+9", "command": "workbench.action.openEditorAtIndex9" }
]
```

---

```json
{
  // ---- Editor ----
  "editor.autoClosingBrackets": "always",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit"
  },
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.fontFamily": "Lab Mono",
  "editor.largeFileOptimizations": true,
  "editor.lineHeight": 1.4,
  "editor.tabCompletion": "onlySnippets",
  "editor.acceptSuggestionOnEnter": "on",
  "editor.tabSize": 4,
  "editor.detectIndentation": false,
  "editor.cursorStyle": "line",
  "editor.wordWrap": "on",
  "editor.formatOnSave": true,

  // ---- File Associations ----
  "files.associations": {
    "*.css": "tailwindcss"
  },

  // ---- File Watcher / Search Exclude ----
  "files.watcherExclude": {
    "**/node_modules": true,
    "**/.git": true,
    "**/dist/**": true,
    "**/build/**": true
  },
  "search.exclude": {
    "**/node_modules": true,
    "**/.git": true,
    "**/dist/**": true,
    "**/build/**": true
  },

  // ---- Explorer / Workbench UI ----
  "explorer.compactFolders": false,
  "explorer.confirmDelete": false,
  "explorer.confirmPasteNative": false,
  "explorer.confirmDragAndDrop": false,
  "workbench.enableExperiments": false,
  "workbench.tree.indent": 20,
  "workbench.tree.renderIndentGuides": "none",

  // ---- Terminal ----
  "terminal.integrated.cursorStyle": "line",
  "terminal.integrated.fontSize": 12,

  // ---- Language-Specific Formatters ----
  "[prisma]": {
    "editor.defaultFormatter": "Prisma.prisma",
    "editor.tabSize": 4
  },
  "[snippets]": {
    "editor.defaultFormatter": "vscode.json-language-features",
    "editor.tabSize": 4
  },
  "[yaml]": {
    "editor.tabSize": 4,
    "editor.guides.bracketPairs": false,
    "editor.guides.bracketPairsHorizontal": false
  },
  "[dockercompose]": {
    "editor.tabSize": 4,
    "editor.guides.bracketPairs": false,
    "editor.guides.bracketPairsHorizontal": false
  },
  "[markdown]": {
    "editor.tabSize": 4,
    "editor.guides.bracketPairs": false,
    "editor.guides.bracketPairsHorizontal": false
  },

  // ---- TS and JS Settings ----
  "javascript.updateImportsOnFileMove.enabled": "always",
  "typescript.updateImportsOnFileMove.enabled": "always",
  "javascript.preferences.quoteStyle": "double",
  "typescript.preferences.quoteStyle": "double",
  "javascript.format.semicolons": "insert",
  "typescript.format.semicolons": "insert",

  // ---- Extensions Behavior ----
  "extensions.autoUpdate": true,
  "extensions.ignoreRecommendations": true,

  // ---- Markdown Previewer ----
  "markdown.preview.fontFamily": "Dank Mono",

  // ---- Misc ----
  "json.schemaDownload.enable": true,
  "update.mode": "default",
  "window.zoomLevel": 1,
  "workbench.fontAliasing": "none",

  // ---- Hide UI Elements ----
  "window.commandCenter": false,
  "breadcrumbs.enabled": false,
  "editor.minimap.autohide": true,
  "redhat.telemetry.enabled": true,
  "workbench.startupEditor": "none",
  "workbench.iconTheme": "flow-deep",
  "flow-icons.hidesExplorerArrows": true,
  "editor.accessibilitySupport": "off",
  "workbench.editor.showTabs": "multiple",
  "git.confirmSync": false,
  "git.openRepositoryInParentFolders": "never"
}
```

---

### 🧩 **VSCode Extensions**

| #   | Extension                   | What it is / Why you use it          | Common Use Case                 | Example                        |
| --- | --------------------------- | ------------------------------------ | ------------------------------- | ------------------------------ |
| 1   | `Docker`                    | VSCode integration for Docker        | Manage containers inside editor | View running containers        |
| 2   | `Prisma`                    | Prisma schema + DB tooling support   | Work with ORM schemas easily    | Edit `schema.prisma`           |
| 3   | `Code Runner`               | Run code snippets instantly          | Quick test JS/TS/Python code    | Run selected code block        |
| 4   | `Container Tools`           | Manage containers in VSCode          | Inspect Docker environments     | View logs of containers        |
| 5   | `Dev Containers`            | Develop inside containers            | Consistent dev environments     | Open project in container      |
| 6   | `Dotenv`                    | `.env` file support                  | Highlight and manage env vars   | Edit `.env` safely             |
| 7   | `ESLint`                    | JavaScript/TypeScript linter         | Enforce code quality rules      | Show lint errors live          |
| 8   | `Flow Icons`                | File/folder icon theme               | Improve project readability     | Visual file structure          |
| 9   | `HTML CSS Support`          | Autocomplete for HTML/CSS            | Faster frontend coding          | Suggest CSS classes            |
| 10  | `Path Intellisense`         | Autocomplete file paths              | Avoid broken imports            | `import './components/Button'` |
| 11  | `Prettier`                  | Code formatter                       | Auto-format code consistently   | Format on save                 |
| 12  | `Tailwind CSS`              | Tailwind autocomplete + hints        | Faster UI development           | Suggest utility classes        |
| 13  | `Template String Converter` | Convert strings to template literals | Clean string interpolation      | `"Hello ${name}"`              |
| 14  | `Terraform`                 | Terraform syntax + tooling           | Infrastructure as code support  | Edit `.tf` files               |
| 15  | `GraphQL`                   | GraphQL language support             | Query + schema development      | Write GraphQL queries          |
 