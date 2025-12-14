# Kumu Decoration Code

Paste this into Kumu's Advanced Editor to style the map.

## Full Decoration Code

```scss
@settings {
  /* Color elements by type */
  element-color: categorize("Type", set(
    "Person" "#5A8A6E",
    "Organization" "#3D6B99"
  ));

  /* Scale elements by number of connections */
  element-scale: scale("degree", 0.5, 2);

  /* Default layout */
  layout: force;
}

@controls {
  /* Filter by sector */
  filter {
    by: "Sector";
  }

  /* Filter by type */
  filter {
    by: "Type";
  }

  /* Search */
  search {}
}
```

## Color Reference

| Type | Color | Hex |
|------|-------|-----|
| Person | Green | #5A8A6E |
| Organization | Blue | #3D6B99 |

## Sector Colors (Optional)

If you want to color by sector instead of type:

```scss
@settings {
  element-color: categorize("Sector", set(
    "FinTech" "#2E7D32",
    "HealthTech" "#1565C0",
    "DeepTech" "#6A1B9A",
    "Social Enterprise" "#EF6C00"
  ));
}
```
