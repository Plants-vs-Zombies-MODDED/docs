---
icon: function
---

# UnloadMenu

Removes a previously loaded menu from the DOM.

### Signature

```javascript
UnloadMenu(menuId) => Promise<void>
```

### Parameters

* `menuId`\
  The ID passed to `LoadMenu`.

### Behavior

* Finds the container by `id="dMenu_<menuId>"`.
* Removes it from its parent, if present.
* Removes `menuId` from [`visibleMenus`](../visiblemenus.md).

### Notes

* Safe to call if the menu is already gone.
* Does not decrement [`menusAmount`](../menusamount.md).

If your menu script binds global listeners, clean them up yourself. DOM removal only cleans listeners bound inside `menuContainer`.
