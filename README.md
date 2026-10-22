# Master Robe Builder

A parametric wardrobe configurator in a single HTML file. Set the cavity, the sections, the partitions and what goes in each section, and the page rebuilds a 3D model, a dimensioned elevation, live clearance checks, a cut list with sheet layouts and a hardware list.

Open `index.html` in a browser, or use the GitHub Pages site. Nothing to install; the only dependency, three.js r128, loads from cdnjs.

## What you can change

- **Cavity:** width, height, depth (wall reveal plus the depth added in front), side and back gaps, carcass depth, main top height.
- **Sections:** how many; each one's width (fixed, auto, the same as another section, fitted to an obstruction, or balancing so the middle stays centred), top height and kicker.
- **Contents:** each section is a stack of zones: drawers, hanging, adjustable shelves or open space, with a fixed shelf between zones. Drawer stacks are built from stock drawer sizes (by box height), so rows line up across sections.
- **Partitions:** end panels and partitions, each single or doubled, every leaf with its own height (auto, a number, or up to the ceiling).
- **Obstruction:** something in the cavity to keep clear of, with its position, size and an optional bottom-hinged door whose swept space is checked against every part. Off by default.
- **Sliding doors:** count, finishes, which finish runs on the outer track, rail length, overlap, fascia. Drag a door in the 3D view to slide it; pushing a door into the next one on its track moves both at half speed.
- **Shoes:** pairs of shoes in the end sections (dress shoes on the bottom of the hanging space, casual ones in the cubby below), men's or women's on each side. The shoes are modelled in the page itself.
- **Materials:** board thicknesses (16 mm by default), drawer allowances, sheet size, kerf and trim.

## Configurations

The **Configuration** menu at the top switches between the built-in designs (AAGL - A to D and the company's rev.01, rev.02 and rev.04) and any you add. The circled **+** adds a configuration as a copy of the one you are looking at, under a name you choose; the circled **−** removes the one you are looking at (removed built-in ones can be brought back from Files and settings). Each configuration keeps its own edits in your browser.

## Keeping and sharing a design

Settings are saved in your browser as you go. **Copy settings** puts the design on the clipboard as JSON; paste it into the box under Files and settings to load it again. **Copy cut list as CSV** gives a spreadsheet-ready cut list.

## Locked design

A private design can sit next to the page as `design.lock.json`, encrypted with a password (AES-256-GCM, key from PBKDF2-SHA256 with 600 000 rounds and a random salt). When that file is present, the page shows **Unlock my design**; the right password loads the private versions of the configurations into the browser, and **Forget my design on this device** clears it again.

To make or replace the file: open the builder, set the design up, then under Files and settings open **Encrypt every configuration for publishing**, enter a password twice and save the result as `design.lock.json` in the repository root. The password never leaves the browser and is never stored. Use a long one (four or more random words): the file is public, so anyone can copy it and try passwords offline.

## Notes

Clearances, sag and hardware figures are a design aid, not a substitute for checking dimensions on site and the supplier's specifications.
