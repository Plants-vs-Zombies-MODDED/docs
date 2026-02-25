---
icon: star
---

# Primary Operations

These are the three functions you use to manage menus.

### Typical flow

1. Optionally warm up assets with [`PreloadMenu`](preloadmenu.md).
2. Show the menu with [`LoadMenu`](loadmenu.md).
3. Remove it with [`UnloadMenu`](unloadmenu.md).

### Guidance for menu scripts

Write your menu JS to only touch `menuContainer`. That keeps cleanup simple on `UnloadMenu`.

Prefer scoped queries:

```javascript
const closeBtn = menuContainer.querySelector("[data-action='close']");
closeBtn?.addEventListener("click", () => UnloadMenu(menuId));
```

Use `extraData` for dynamic input. Avoid reaching into unrelated globals when possible.

{% hint style="info" %}
Avoid loading the same `menuId` twice. Duplicate `id="dMenu_<menuId>"` breaks `UnloadMenu`.
{% endhint %}
