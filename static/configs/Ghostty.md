## 🐚 Ghostty Configuration

---

```json
font-family = "DankMono Nerd Font Mono"
font-style = "DankMono Nerd Font Mono Bold"

font-size = 20
font-thicken = **true**

cursor-style = bar
cursor-style-blink = true
cursor-color = #F8F8F2

font-feature = -calt
font-feature = -liga
font-feature = -dlig

theme = tokyonight_moon

window-padding-x = 16
window-padding-y = 12
window-decoration = true
macos-titlebar-style = tabs
background-opacity = 0.9
background-blur-radius = 20
adjust-cell-height = 10

shell-integration = zsh
shell-integration-features = cursor,sudo,title

scrollback-limit = 10000

mouse-hide-while-typing = true
focus-follows-mouse = false

keybind = cmd+t=new_tab
keybind = cmd+w=close_surface
keybind = cmd+shift+f=text:yazi\n

confirm-close-surface = false
quit-after-last-window-closed = true
```


## 📁 Yazi Configuration

---

1. Create `~/.config/yazi/yazi.toml`
2. Put it 

```toml
[mgr]
show_hidden = true

[opener]
edit = [
    { run = 'code --wait "$@"', block = true, desc = "VS Code" }
]

[open]
rules = [
    { name = "*", use = "edit" }
]
```

