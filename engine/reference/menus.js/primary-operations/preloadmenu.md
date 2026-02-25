---
icon: function
---

# PreloadMenu

Fetches a menu’s HTML and JS into the browser cache. It does not create DOM nodes.

### Signature

```javascript
PreloadMenu(menuId) => Promise<void>
```

### Parameters

* `menuId`\
  Used to fetch `menu/html/<menuId>.html`.\
  Used to fetch `menu/js/<menuId>.js`.

### Behavior

* Always requests the HTML file.
* Requests the JS file, if it exists.
* Ignores missing JS.

### Errors

Network errors bubble up. HTTP errors like `404` do not reject `fetch` by themselves.

If the server returns an error HTML body, it still gets cached.

### Example

```javascript
await PreloadMenu("Options");
```
