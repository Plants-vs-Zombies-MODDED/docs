---
icon: browsers
---

# Menu System

The menu system loads UI overlays at runtime.

Each menu is HTML plus optional JavaScript. Menus mount into `#dAll` or `#dSurface`.

### Menu assets

Store menu markup here:

* `menu/html/<menuId>.html`

Store menu logic here:

* `menu/js/<menuId>.js` (optional)

`<menuId>` is the identifier you pass to `LoadMenu`.

### Where menus render

Menus default to `#dAll`. If `#dSurface` exists and is visible, it is used.

This lets the game swap menu layers without changing your call sites.

### Stacking and state

Menus are full-screen `div`s with `position: absolute`. Each menu gets a higher `z-index` than the last one.

State lives in these globals:

* [`visibleMenus`](visiblemenus.md)
* [`menusAmount`](menusamount.md)

DOM discovery uses:

* [`getDAll`](getdall.md)

### Core API

Use these three operations most of the time:

* [`PreloadMenu`](primary-operations/preloadmenu.md)
* [`LoadMenu`](primary-operations/loadmenu.md)
* [`UnloadMenu`](primary-operations/unloadmenu.md)

Read the flow guide in [Primary Operations](primary-operations/).

{% hint style="warning" %}
`LoadMenu` runs menu scripts using `new Function(...)`. Only load trusted menu JS.
{% endhint %}
