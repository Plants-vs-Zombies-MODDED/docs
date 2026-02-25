---
icon: function
---

# CustomSpecial

Places a plant.

### Signature

```javascript
CustomSpecial(PlantClass, row, column, extraArgs?) => Plant
```

### Parameters

* `PlantClass`\
  The class of the desired plant.
* `row`\
  The row the plant will be placed on.
* `column`\
  The column the plant will be placed on.
* `extraArgs`\
  Optional. Class-specific configuration passed to `Birth`.

### Behavior

Calls the requested `PlantClass`'s `Birth` method with `extraArgs` passed at the end.

### Returns

Returns the instantiated plant object.

### Example

```javascript
// Spawn a Peashooter at the 4th row and 3rd column
CustomSpecial(oPeashooter, 4, 3);
```
