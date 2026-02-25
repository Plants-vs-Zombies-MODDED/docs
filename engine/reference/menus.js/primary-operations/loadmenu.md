---
icon: function
---

# LoadMenu

Loads a menu overlay, injects its HTML, then runs its JS.

### Signature

```javascript
LoadMenu(menuId, background, extraData = {}, debounceElement) => Promise<HTMLDivElement>
```

### Parameters

* `menuId`\
  Menu identifier.\
  Used for asset URLs and the container ID.
* `background`\
  Optional background image URL.\
  Applied as `background: url(...) no-repeat`.
* `extraData`\
  Object passed into the menu script.\
  Default is `{}`.
* `debounceElement`\
  Optional DOM element to mark while loading.\
  Toggles the `cantSelect` class during fetch.

### Behavior

* Ensures `#dAll` exists via [`getDAll`](../getdall.md).
* Chooses render target:
  * `#dSurface` if it exists and `display === "block"`.
  * Otherwise `#dAll`.
* Creates a full-screen container: `id="dMenu_<menuId>"`.
* Sets `z-index` to `9999 + menusAmount`.
* Appends HTML before running the menu script.
* Runs `menu/js/<menuId>.js` with `new Function(...)`.

The script receives:

* `menuContainer`
* `menuId`
* `extraData`

After mounting, it updates [`visibleMenus`](../visiblemenus.md).

### Returns

The created menu container element.

### Errors

* Rejects if `#dAll` never appears in time.
* Rejects on network errors during `fetch`.
* Does not reject on HTTP `404` by itself.
* Throws if the menu JS throws.

### Example

```javascript
const menu = await LoadMenu("Options", null, { from: "pause" });
menu.classList.add("fade-in");
```

{% hint style="warning" %}
Do not load the same `menuId` twice at once. `UnloadMenu` uses `getElementById`, which becomes ambiguous.
{% endhint %}
