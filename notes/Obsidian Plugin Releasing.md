# **`🗓️ 17.04.2026`**

A clean summary of the main lessons learned while building the **Obicard** Obsidian plugin.

> [!NOTE] These notes explain how Obsidian plugins are built, versioned, and delivered to users through GitHub.

---

## 🚀 How Obsidian Plugin Delivery Works

Obsidian plugins do **not** rely on a central server. Instead, they use **GitHub Releases** and **GitHub Actions** to build and distribute plugins.

### 📦 Files Obsidian actually uses

Obsidian only needs three files from a plugin:

| File | Purpose |
|------|---------|
| `main.js` | The compiled plugin logic |
| `manifest.json` | Plugin identity and metadata |
| `styles.css` | Plugin styles, such as layout or grid styling |

> [!IMPORTANT] If these three files are correct, Obsidian can load the plugin properly.

### ⚙️ Why GitHub Actions is useful

GitHub Actions builds the plugin in a clean environment.

- It runs on a remote server
- It avoids local machine issues
- It removes problems caused by:
  - different Node.js versions
  - cached files
  - local setup differences

> [!TIP] If the plugin builds successfully in GitHub Actions, it is much more likely to work for users too.

### 🔄 How Obsidian gets plugin updates

Obsidian checks your repository and looks at the **Releases** section.

1. It opens your GitHub repository.
2. It goes to **Releases**.
3. It finds the latest release.
4. It downloads the three plugin files from that release.

### ✅ Why this workflow is good

| Side | Benefit |
|------|---------|
| Obsidian team | No need to host thousands of plugin files themselves |
| Developer | No manual uploading to a separate store |
| User | Gets a stable, frozen release version |

> [!SUCCESS] Even if the `main` branch breaks later, users stay safe because they download the last published release, not the live development branch.

---

## 🔁 Typical Release Workflow

This is the usual process for publishing a plugin update:

1. Develop the feature locally.
2. Test it in Obsidian.
3. Update the version in `manifest.json`  
   - Example: `1.0.0` → `1.0.1`
4. Push the changes to GitHub.
5. Create a new GitHub Release with the matching tag.
6. GitHub Actions builds the plugin.
7. The release gets the new compiled `main.js`.
8. Users see the update in Obsidian.

> [!EXAMPLE] Example: after finishing a feature like **Peek mode**, you bump the version to `1.0.1`, create a release, and GitHub Actions prepares the final build.

---

## 🏷️ Versioning and Tags

The project includes a script called `version-bump.mjs` and a related script in `package.json`.

### What the version script does

- Updates the version automatically
- Saves time
- Reduces manual mistakes

### Example command

```bash
npm version 1.0.1
```

### Pushing version changes

After updating the version, push everything including tags:

```bash
git push origin main --tags
```

### What is a Git tag?

A **tag** is a permanent marker on a specific commit.

- A **branch** keeps moving forward
- A **tag** stays attached to one exact commit

Tags are usually named like this:

- `v1.0.0`
- `v1.0.1`

> [!IMPORTANT] Tags are important because releases are tied to exact code states.

---

## 🧱 Plugin Structure

The main entry point of an Obsidian plugin is `main.ts`.

### `main.ts`

This file is loaded first. Obsidian looks for a class that extends `Plugin`.

### Main lifecycle methods

| Method | Purpose |
|--------|---------|
| `onload()` | Runs once when the plugin is enabled |
| `onunload()` | Runs when the plugin is disabled |

### `onload()`

This is the most important method.

Use it to register plugin features such as:

- buttons in the left sidebar
- commands in the command palette
- event listeners
- UI elements

> [!TIP] Think of `onload()` as the place where the plugin “starts living.”

### `onunload()`

This is the cleanup method.

Use it to:

- remove listeners
- clear timers
- free memory
- clean up UI elements

> [!IMPORTANT] Good cleanup helps prevent memory leaks and weird behavior after disabling the plugin.

---

## 🧠 Key Takeaways

- Obsidian plugins are distributed through **GitHub Releases**
- Only **three files** are needed by Obsidian:
  - `main.js`
  - `manifest.json`
  - `styles.css`
- **GitHub Actions** builds the plugin in a clean environment
- **Version tags** are essential for stable releases
- `onload()` is where plugin features are registered
- `onunload()` is where cleanup happens
