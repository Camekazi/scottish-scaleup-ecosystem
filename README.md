# Scottish Scale-Up Ecosystem Network Map

An interactive network visualization of Scotland's scale-up ecosystem - founders, investors, accelerators, and the connections between them.

## Live Map

**Kumu**: [scottish-scaleup-ecosystem](https://kumu.io/camekazi/scottish-scaleup-ecosystem)

**Data Source**: [Google Sheet](https://docs.google.com/spreadsheets/d/1je0yoVeW_RBPMuKH2fD17c4afxOcoE8DFFsQiyVoOeU)

## What This Is

A public, community-maintainable map of the Scottish tech and scale-up ecosystem. Visualizes:
- **People**: Founders, CEOs, investors, advisors, ecosystem builders
- **Organizations**: Scale-ups, accelerators, investors, government bodies
- **Connections**: Who works where, who founded what, advisory relationships

## Scale-Up Definition

We use the **OECD/Eurostat definition** adopted by the ScaleUp Institute:

| Criteria | Threshold |
|----------|-----------|
| Employees | **10+** at start of observation |
| Growth | **20%+ annual** (employees OR revenue) |
| Duration | **3 consecutive years** |

**Scottish Programme Threshold**: >£500k turnover, >5 employees, 20%+ growth

### Classification

| Status | Meaning | Color in Kumu |
|--------|---------|---------------|
| `scale-up` | Meets OECD criteria | 🟢 Green |
| `unicorn` | £1B+ valuation | 🟣 Purple |
| `ecosystem` | Supports scale-ups (accelerators, govt, investors) | 🔵 Blue |
| `pre-scale` | Potential but <10 emp or <3yr track record | 🟡 Amber |
| `unknown` | Needs verification | ⚫ Grey |

**Sources**:
- [OECD SME Scale-Up](https://www.oecd.org/cfe/smes/sme-scale-up.htm)
- [ScaleUp Institute Scotland](https://www.scaleupinstitute.org.uk/scaleup-review-2023/scotland/)
- [Scottish Tech Ecosystem Review](https://www.gov.scot/publications/scottish-technology-ecosystem-review/)

## Data Structure

### Google Sheet Tabs

| Tab | Contents |
|-----|----------|
| **Elements** | People + Organizations |
| **Connections** | Relationships between elements |
| **Legend** | Definitions, criteria, color codes |

### Elements Columns

| Column | Required | Description |
|--------|----------|-------------|
| ID | ✅ | UUID for stable identity (e.g., `d407aa5e-2c32-4007-add2-56110aa3aea1`) |
| Label | ✅ | Name (person or organization) |
| Type | | Person / Organization |
| Description | | Public role or description |
| Sector | | FinTech, HealthTech, DeepTech, Social Enterprise |
| LinkedIn | | Public LinkedIn URL |
| ScaleUpStatus | | scale-up, unicorn, ecosystem, pre-scale, unknown |
| StatusNotes | | Justification for classification |

> **Note**: The ID column ensures data integrity—you can rename Labels without breaking connections.

### Connections Columns

| Column | Required | Description |
|--------|----------|-------------|
| From | ✅ | Source element Label |
| To | ✅ | Target element Label |
| Type | | works_at, founded, advises, invested_in, etc. |

## How to Contribute

### Add Someone
Open an [Issue](../../issues/new?template=add-entry.yml) with:
- Name and role
- Organization
- Employee count / growth info (for scale-up validation)
- Any known connections

### Report an Error / Request Removal
Open an [Issue](../../issues/new?template=report-issue.yml). Removal requests honored within 7 days.

### Direct Edit (Trusted Contributors)
Request edit access to the [Google Sheet](https://docs.google.com/spreadsheets/d/1je0yoVeW_RBPMuKH2fD17c4afxOcoE8DFFsQiyVoOeU).

## Privacy

- **Public figures only**: CEOs, founders, and professionals with public LinkedIn profiles
- **No private data**: No contact details, no strategic notes, no relationship assessments
- **Removal on request**: Anyone can request removal of their information

## Technical Details

```
Google Sheets → Kumu (direct integration, auto-sync on refresh)
```

- **Data**: Google Sheets with 3 tabs (Elements, Connections, Legend)
- **Visualization**: [Kumu](https://kumu.io) with direct Sheets integration
- **Updates**: Edit Sheet → Refresh Kumu → Done
- **Filtering**: Use Kumu controls to filter by ScaleUpStatus, Sector, or Type

### Kumu Filter: Show Only Scale-Ups

In Kumu's Advanced Editor:
```scss
@settings {
  focus: ScaleUpStatus = "scale-up" or ScaleUpStatus = "unicorn";
}
```

## Local Development

No code required! This project uses Kumu's direct Google Sheets integration.

To update the map:
1. Edit the [Google Sheet](https://docs.google.com/spreadsheets/d/1je0yoVeW_RBPMuKH2fD17c4afxOcoE8DFFsQiyVoOeU)
2. Refresh the Kumu page
3. Changes appear immediately

## License

Data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) - Attribution required for reuse.

---

*Part of the [Scottish Tech Ecosystem](https://www.gov.scot/publications/scottish-technology-ecosystem-review/)*
