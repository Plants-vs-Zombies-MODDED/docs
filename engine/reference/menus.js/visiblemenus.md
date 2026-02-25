---
icon: square-root-variable
---

# visibleMenus

Array of menu IDs that are currently loaded.

`LoadMenu` pushes into it. `UnloadMenu` removes from it.

### Notes

* Order is the load order.
* It is not a count.
* It is not automatically repaired if you remove DOM manually.

### Example

```javascript
const topMenuId = visibleMenus.at(-1);
```
