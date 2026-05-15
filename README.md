# 🌳 Annex Tree Map

Community-Sourced Urban Forest Data for Toronto’s Annex Neighbourhood
https://atm.xyz.am

## 📍 Overview

The **Annex Tree Map** is a community-driven project to preserve, visualize, maintain, and expand the historical tree inventory collected in Toronto’s Annex neighbourhood between **2010 and 2014**.

Originally surveyed by neighbourhood volunteers through the **Annex Residents’ Association (ARA)**, the dataset documents thousands of trees, including species, diameter, height, condition notes, and geographic coordinates.

The project now provides a public, interactive map at:

➡️ **https://atm.xyz.am**

---

## ✅ Current Dataset Status

The Annex Tree Map dataset has been cleaned and normalized.

- **10,134 trees**
- **Unique 8-digit tree IDs**
- Tree IDs range from `00000001` to `00010134`
- **Zero duplicate tree IDs confirmed**
- Dataset maintained as GeoJSON/JSON for public use and community improvement

This unique ID system makes it easier to reference, correct, update, and expand individual tree records over time.

---

## 🗺️ Live Interactive Map

The interactive map is available here:

**https://atm.xyz.am**

The map uses **OpenStreetMap** and **Leaflet** to display Annex tree data and supports browsing and filtering by tree information such as:

- Species
- Street
- Tree size / DBH ranges
- Individual tree records

---

## 🌲 Data Source & Credits

The original dataset comes from the **Annex Residents’ Association Tree Mapping Project**, conducted between **2010 and 2014**.

Neighbourhood volunteers collected information including:

- Tree species
- Street address
- DBH — Diameter at Breast Height
- Height
- Number of stems
- Comments and condition notes
- Geographic coordinates

The original data was published through the ARA website and exported as GeoJSON. This repository helps preserve that work while making the data easier to maintain, correct, and expand.

---

# 📁 Repo Structure
/data
   annex-trees.json     → Main GeoJSON dataset

README.md               → You are here

# 🛠️ Contributing

We welcome pull requests for:

Fixing incorrect coordinates

Correcting tree heights or DBH anomalies

Adding missing street names

Cleaning species names

Adding new tree observations

Improving map functionality

1. Fixing Data

If you spot errors:

Open an Issue

Describe the problem (tree_no, location, expected value)

Submit a Pull Request with the fix

# 🧰 Adding New Trees (JSON Generator)

Visit:

➡️ https://annextrees.xyz.am

Scroll to the JSON Generator tool.

It will output a properly formatted GeoJSON fragment like:

```html

{
  "type": "Feature",
  "properties": {
    "Date": "2024",
    "tree_no": "987",
    "house_number": "42",
    "street_code": "Kendal Ave",
    "species_code": "acrsac",
    "tree_name": "Sugar Maple",
    "n_o_s": "1.0",
    "DBH": "28.0",
    "total_height": "8.5",
    "Comments": "",
    "X coordinate": -79.405501,
    "Y coordinate": 43.673770
  },
  "geometry": {
    "type": "Point",
    "coordinates": [ -79.405501, 43.673770 ]
  }
}
```

Paste this directly into annex-trees.json.

Need coordinates?
Use the companion tool:
📌 https://coordinates.xyz.am

🔗 Embedding the Map

You can embed the tree map in any site using:

```html
<iframe
  src="https://annextreemap.xyz.am/"
  width="100%"
  height="600"
  style="border:0;"
></iframe>
```


# 🧪 Data Quality Notes

During cleaning, several issues were identified:

~345 trees with coordinates (0,0)

A few unrealistic heights (e.g., 200m)

Some missing street names

Some text-based numeric fields (“6.2” instead of numbers)

Duplicate coordinates due to surveying from the same point

Issues have been documented in GitHub for transparency.

# 📸 Screenshot

![Annex Tree Map Screenshot](https://github.com/ptoone/annex-tree-map/blob/main/data/annextrees.png?raw=true)

# 📝 License

This project is open data.
Attribution to the Annex Residents’ Association is appreciated.
