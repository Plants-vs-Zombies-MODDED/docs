---
icon: square-root-variable
---

# menusAmount

Monotonic counter for menu loads.

`LoadMenu` increments it before creating a menu container. The value is used to compute `z-index`.

### Notes

* It does not decrement on `UnloadMenu`.
* It is not the number of visible menus.

If you need the visible count, use [`visibleMenus`](visiblemenus.md).
