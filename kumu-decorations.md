# Kumu Decoration Code

Paste this into Kumu's Advanced Editor to style the map.

## Full Decoration Code

```scss
@settings {
  /* Color by ScaleUpStatus */
  element-color: categorize("ScaleUpStatus", set(
    "scale-up" "#2E7D32",
    "unicorn" "#6A1B9A",
    "ecosystem" "#1565C0",
    "pre-scale" "#F9A825",
    "unknown" "#757575"
  ));

  /* Scale elements by number of connections */
  element-scale: scale("degree", 0.5, 2);

  /* Default layout */
  layout: force;
}

@controls {
  /* Filter by ScaleUpStatus - KEY FILTER */
  filter {
    by: "ScaleUpStatus";
  }

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

## Show ONLY Scale-Ups (Focus Mode)

To show only actual scale-ups and unicorns (hide ecosystem builders):

```scss
@settings {
  focus: ScaleUpStatus = "scale-up" or ScaleUpStatus = "unicorn";
}
```

## Color Reference

| ScaleUpStatus | Color | Hex | Meaning |
|---------------|-------|-----|---------|
| scale-up | Green | #2E7D32 | Meets OECD criteria (10+ emp, 20%+ growth) |
| unicorn | Purple | #6A1B9A | £1B+ valuation |
| ecosystem | Blue | #1565C0 | Supports scale-ups (accelerators, govt, investors) |
| pre-scale | Amber | #F9A825 | Potential but not yet qualifying |
| unknown | Grey | #757575 | Needs verification |

## Scale-Up Definition (OECD/Eurostat)

A company qualifies as a **scale-up** if:
- **10+ employees** at start of observation period
- **20%+ average annual growth** (employees OR revenue) over **3 consecutive years**

Scottish threshold: >£500k turnover, >5 employees, 20%+ growth

**Sources:**
- [OECD SME Scale-Up](https://www.oecd.org/cfe/smes/sme-scale-up.htm)
- [ScaleUp Institute Scotland](https://www.scaleupinstitute.org.uk/scaleup-review-2023/scotland/)
- [Scottish Tech Ecosystem Review](https://www.gov.scot/publications/scottish-technology-ecosystem-review/)

## Alternative: Color by Type

```scss
@settings {
  element-color: categorize("Type", set(
    "Person" "#5A8A6E",
    "Organization" "#3D6B99"
  ));
}
```

## Alternative: Color by Sector

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
