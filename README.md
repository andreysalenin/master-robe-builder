# Master Robe Builder

A parametric wardrobe configurator in a single HTML file. Set the cavity, the sections, the partitions and what goes in each section, and the page rebuilds a 3D model, a dimensioned elevation, live clearance checks, a cut list with sheet layouts and a hardware list.

Use the GitHub Pages site, or serve the folder (the shoe models load from `shoes/`). Nothing to install; the only dependency, three.js r128, loads from cdnjs.

## What you can change

- **Cavity:** width at the front and at the back (for a cavity out of square), height, depth (wall reveal plus the depth added in front), carcass depth, main top height, and the packing between the end panels and the walls at the front and the back.
- **Symmetry:** the page measures whether the drawers are centred on the sliding-door opening, the drawer sections mirror each other and the doors read the same both ways, says plainly whether the design is truly symmetric, and dimensions it over the elevation.
- **Sections:** how many; each one's width (fixed, auto, the same as another section, fitted to an obstruction, or balancing so the middle stays centred), top height and kicker.
- **Contents:** each section is a stack of zones: drawers, hanging, adjustable shelves or open space, with a fixed shelf between zones. Drawer stacks are built from stock drawer sizes (by box height), so rows line up across sections.
- **Partitions:** end panels and partitions, each single or doubled, every leaf with its own height (auto, a number, or up to the ceiling).
- **Obstruction:** something in the cavity to keep clear of, with its position, size and an optional bottom-hinged door whose swept space is checked against every part. Off by default.
- **Wall posts:** timber posts standing proud of the side walls near the front, with how far each one stands out, where it sits front to back and the cladding round it. Fitted to them, the end panels line up with the cladding, which sets the side gaps, and the door rail runs between the clad posts. The outer end panels can carry on forward to the posts (up to the top shelf under the top, then floor to ceiling in front of it), and the tops can run over the end panels to the side walls.
- **Storage containers:** containers of any width, length and height on the tops, spread along them. Take one out (play or scrub, in the 3D view or the side view) and the page checks every step of the way against the fascia, the door track behind it, the ceiling and anything else in line, and gives the tallest container that clears. They are the same in every configuration.
- **Sliding doors:** count, finishes, which finish runs on the outer track, rail length, overlap, fascia. Above the doors, a wall element (bulkhead, lintel or the timber the track fixes to) and the hollow aluminium top track the doors hang from, each with its height and depth; by default the fascia covers the two of them (60 + 40 = 100). Drag a door in the 3D view to slide it; pushing a door into the next one on its track moves both at half speed.
- **Shoes:** two pairs a row in the end sections (dress shoes on the bottom of the hanging space, casual ones in the cubby below), men's or women's on each side, staggered front and back where the section is too narrow for them side by side. The eight shoe models in `shoes/` were made for this project; if they can't load (a page opened on its own), simpler built-in shapes stand in.
- **Walls:** the room's walls painted in the 3D view and the elevation: the side walls one colour, the back wall a colour for each section above and below its top shelf. The Walls chip over the 3D view shows or hides them.
- **Materials:** board thicknesses (16 mm by default), drawer allowances, sheet size, kerf and trim.

## Configurations

The **Configuration** menu at the top switches between the built-in designs (AAGL - A to G and the company's rev.01, rev.02 and rev.04) and any you add. The circled **+** adds a configuration as a copy of the one you are looking at, under a name you choose; the circled **−** removes the one you are looking at (removed built-in ones can be brought back from Files and settings). Each configuration keeps its own edits in your browser.

## Keeping and sharing a design

Settings are saved in your browser as you go. **Copy settings** puts the design on the clipboard as JSON; paste it into the box under Files and settings to load it again. **Copy cut list as CSV** gives a spreadsheet-ready cut list.

## Locked design

A private design can sit next to the page as `design.lock.json`, encrypted with a password (AES-256-GCM, key from PBKDF2-SHA256 with 600 000 rounds and a random salt). When that file is present, the page shows **Unlock my design**; the right password loads the private versions of the configurations into the browser, and **Forget my design on this device** clears it again.

To make or replace the file: open the builder, set the design up, then under Files and settings open **Encrypt every configuration for publishing**, enter a password twice and save the result as `design.lock.json` in the repository root. The password never leaves the browser and is never stored. Use a long one (four or more random words): the file is public, so anyone can copy it and try passwords offline.

## Notes

Clearances, sag and hardware figures are a design aid, not a substitute for checking dimensions on site and the supplier's specifications.
