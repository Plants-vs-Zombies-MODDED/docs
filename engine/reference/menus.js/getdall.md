---
icon: function
---

# getDAll

Returns the `#dAll` container, waiting for it if needed.

### Signature

```javascript
getDAll({ timeoutMs = 5000 } = {}) => Promise<HTMLElement>
```

### Parameters

* `timeoutMs`\
  Max wait time for `#dAll`.\
  Default is `5000`.

### Behavior

* Returns immediately if `#dAll` already exists.
* Waits for `DOMContentLoaded` if the DOM is still loading.
* Observes DOM mutations for late insertion of `#dAll`.

### Errors

Rejects if `#dAll` never appears within `timeoutMs`. The thrown error message mentions `LoadMenu`.

### Example

```javascript
const dAll = await getDAll({ timeoutMs: 10_000 });
dAll.appendChild(document.createTextNode("ready"));
```
