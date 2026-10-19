# Annex Tree Map

Community-sourced urban forest data for Toronto's Annex neighbourhood.

[Explore the map](https://atm.xyz.am) | [Get involved](https://atm.xyz.am/get-involved.php) | [Recent updates](https://atm.xyz.am/updates.php)

## Overview

The Annex Tree Map preserves, visualizes, maintains, and expands the historical tree inventory collected by neighbourhood volunteers through the Annex Residents' Association (ARA) between 2010 and 2014.

The public website makes tree records easier to explore and gives the community ways to suggest corrections, add observations, and maintain the dataset.

## Dataset

The initial ID cleanup assigned unique eight-digit string IDs to 10,134 records, from `00000001` through `00010134`, with no duplicate IDs at that time. Tree counts change as records are added or deleted; these figures describe the cleanup baseline, not a live inventory count.

- The main dataset is `data/annex-trees.json`, a GeoJSON FeatureCollection hosted on GitHub.
- Each record's `tree_no` is a string. Preserve its leading zeros.
- Admin assigns new IDs automatically from the current maximum ID plus one.
- IDs identify records; they are not physical tree tags or street-level survey numbers.

## Explore

- [Interactive map](https://atm.xyz.am/edit.php?view=map): browse tree locations and records.
- [Statistics](https://atm.xyz.am/stats.php): explore species and size distributions.
- [Suggest an edit](https://atm.xyz.am/edit.php): submit a correction without an account.
- [Updates](https://atm.xyz.am/updates.php): follow changes and community suggestions.
- [Embedding options](https://atm.xyz.am/embed.php): share the map on another website.

The map uses OpenStreetMap and Leaflet.

## Contribute

### Spotters

No account is needed. Spotters can suggest changes to existing trees, including species, measurements, location, and notes.

1. Find the tree and note its eight-digit ID.
2. Open the [edit form](https://atm.xyz.am/edit.php).
3. Describe the correction and submit the suggested values.

Suggestions create GitHub issues and remain pending until reviewed and applied. Spotters cannot add new trees through this form.

### Mappers

Mappers have admin access and a GitHub account with collaborator access to the data repository. They can edit existing records, add trees, and delete incorrect records directly.

To express interest, [subscribe by email](https://atm.xyz.am/index.php#subscribe). Subscription does not automatically grant editing access; a Steward must invite you.

Once access is arranged:

1. Accept the GitHub collaborator invitation.
2. Sign in to the [Admin Editor](https://atm.xyz.am/admin.php) with the admin password supplied by the project owner.
3. Connect your GitHub account using the token instructions on that page.
4. Search for a tree to edit, or choose **Add New Tree**.
5. Save the record to commit the change to GitHub.

**Admin changes create commits, not issues.** Check the [commit history](https://github.com/ptoone/annex-tree-map/commits/main/) to verify an edit, addition, or deletion. The public map may take a short time to reflect a change.

Keep passwords and personal access tokens private. Never paste tokens into issues, pull requests, or repository files.

### Stewards

Stewards are trusted maintainers with GitHub access who can invite other Mappers, manage collaborator access, and review community suggestions. Owner-only site management uses a separate superadmin login.

### Pull Requests And Issues

Contributions through GitHub are also welcome:

- Correct coordinates, species, measurements, or missing street information.
- Add verified tree observations.
- Improve the website, documentation, or data validation.

[Open an issue](https://github.com/ptoone/annex-tree-map/issues) with the tree ID, location, current value, proposed correction, and supporting observations. For code or data changes, submit a pull request with a focused description.

## Data Format

Each tree is a GeoJSON Point feature with properties such as:

- `tree_no`: unique eight-digit record ID.
- `Date`: survey year.
- `house_number` and `street_code`: address information.
- `species_code` and `tree_name`: species identification.
- `n_o_s`: number of stems.
- `DBH`: diameter at breast height, in centimetres.
- `total_height`: height in metres.
- `Comments`: field notes.
- `X coordinate` and `Y coordinate`: longitude and latitude.

GeoJSON `geometry.coordinates` uses **[longitude, latitude]** order. When changing a location, keep the coordinate properties and geometry synchronized. Many original measurement fields are stored as strings; preserve the existing schema unless a coordinated migration is planned.

For new trees, use the Admin Editor so it assigns the ID and constructs the feature. Do not copy an existing tree's ID. For manual data pull requests, check ID uniqueness across the entire dataset.

Need coordinates? Use the [coordinate tool](https://coordinates.xyz.am/).

## Repository Structure

```text
data/
  annex-trees.json    Main GeoJSON dataset
README.md            Project documentation
```

The PHP website is deployed separately; the tree data remains hosted on GitHub.

## Data Quality

Historical survey records may contain missing or invalid coordinates, unrealistic measurements, incomplete street information, and shared coordinates. A record may also no longer describe a living tree at that location.

Treat measurements as survey observations, not current verified conditions. Check uncertain records in the field before correcting them, and explain the evidence in your suggestion or pull request. ID cleanup does not establish that every record represents a distinct physical tree.

## Data Source And Credits

The original inventory was collected by Annex Residents' Association volunteers and community members between approximately 2010 and 2014. Their work recorded species, addresses, tree measurements, stems, condition notes, and locations.

This project republishes that survey as GeoJSON and provides tools for its continued improvement. Please acknowledge the original survey organizers and volunteers when reusing the dataset.

The Annex Tree Map was created by [Perry Toone](https://xyz.am/perry), with support from Annex-based [Thexyz](https://thexyz.com). The website is hosted with Thexyz and powered by renewable energy.

## Screenshot

![Annex Tree Map screenshot](https://github.com/ptoone/annex-tree-map/blob/main/data/annextrees.png?raw=true)

## License

Project code is licensed under the [GNU General Public License v3.0](https://github.com/ptoone/annex-tree-map/blob/main/LICENSE). GPL-3.0 is a copyleft license, not a public-domain dedication.

Attribution to the Annex Residents' Association and survey volunteers is appreciated.
