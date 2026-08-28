# Të jetosh në ishull — Interactive Character Map

An interactive, multilingual character map for **_Të jetosh në ishull_** by **Ben Blushi**.

The project visualizes the novel's characters across generations, families, religions, name changes, and narrative relationships. It is designed to work both as a **genealogical family tree** and as an **exploration tool** for a novel with a large cast and several interconnected family branches.

- **Live project:** https://tejetoshneishull.github.io/
- **Repository:** https://github.com/tejetoshneishull/tejetoshneishull.github.io
- **Current dataset:** 67 character nodes and 104 encoded relationships
- **Languages:** Albanian, Italian, English

---

## 1. What the map shows

Each character is represented by a card containing, depending on zoom level:

- nationality/origin flag;
- character name;
- approximate or reconstructed birth year;
- religion;
- religion change, where applicable.

Additional information is available by selecting a character:

- birthplace;
- death year, when known;
- religion at birth and later religion;
- nationality or cultural affiliation;
- family/branch;
- alternative names and aliases;
- notes derived from the novel;
- source references used during reconstruction;
- direct relationships with other characters.

Years preceded by **≈** are estimates or chronological reconstructions rather than explicitly stated dates.

---

## 2. How to read the character cards

The visual encoding of religion is intentionally redundant so that the map remains understandable even when many characters are visible.

- **Red** = Christian
- **Green** = Muslim
- **Blue** = Jewish
- **Grey** = unspecified / other

For a character who changes religion:

- the **inner border** represents religion at birth;
- the **outer halo** represents the later religion;
- the text inside the card also displays the change explicitly, for example `✝ → ☪`.

The flag is used as a compact indication of nationality or geographical/cultural origin.

---

## 3. Family-tree organization

The default view is arranged as a genealogical tree.

Characters are placed:

- **vertically** according to generation/chronology;
- **horizontally** according to family branch.

The current family-tree lanes are:

1. **Voskopoja**
2. **Komneni**
3. **History / ancestors**
4. **Mihali · Zoica**
5. **Xhavella**
6. **Ibrahim family**
7. **Bilali**
8. **Benishi · Bakri**

Some characters deliberately sit **between two columns** because they connect two families through marriage or descent. Examples include:

- Marin Kurila's older sister between **Voskopoja** and **Komneni**;
- Ana Xhavella between **Xhavella** and **Ibrahim**;
- Fatimja between **Ibrahim** and **Bilali**.

This placement is intentional and is meant to make cross-family relationships easier to follow.

---

## 4. Relationship lines

The map distinguishes several kinds of relationships.

### Parent → child
A solid genealogical line with an arrow toward the child.

### Marriage
A gold dashed relationship.

### Partner / relationship
A dotted or lighter gold relationship.

### Sibling / wider kinship
A blue-grey dotted relationship.

### Social / political relationship
A muted dashed relationship used mainly in the **Relationship Network** view.

### Couple junctions
When two people are a couple and have children, the family-tree view often uses a small shared junction between them. Their children descend from that junction instead of drawing two long parent lines for every child.

This reduces visual clutter and follows the logic of conventional genealogical diagrams.

Use the **Legend** button at any time to display the visual key.

---

# Main functionality

## 5. Three visualization modes

### Family Tree

This is the default view and the best view for understanding genealogy.

- Characters are grouped into **25-year generational bands**.
- Family branches occupy stable horizontal lanes.
- Parent/child and couple relationships are prioritized.
- Most social and political links are hidden so that the genealogy remains readable.
- Selecting a person fades unrelated parts of the map.

Use this view when the main question is:

> Who belongs to which family, and how are the generations connected?

---

### Timeline

The Timeline view emphasizes chronology.

- Vertical position follows birth year as closely as possible.
- Family columns are preserved where useful.
- Reconstructed dates remain marked with **≈**.
- Small adjustments are allowed to prevent cards from overlapping.

Use this view when the main question is:

> Which characters belong to the same period or generation?

The chronology is therefore **readability-aware**, not a mathematically exact historical axis.

---

### Relationship Network

This view treats the cast as a broader network rather than only a family tree.

It also displays:

- wider kinship;
- friendships and acquaintances;
- political relationships;
- narrative connections;
- other social links encoded in the dataset.

The layout is force-directed, so nodes are reorganized according to their network connections rather than family columns.

Use this view when the main question is:

> Which characters are connected in the story, even when they are not directly related?

Switching back to **Family Tree** or **Timeline** restores their deterministic layouts.

---

## 6. Search

The search field searches across more than the visible character name.

It can match:

- names;
- aliases;
- family names;
- notes;
- birthplace;
- nationality/affiliation.

Matching characters remain visible and the map automatically moves toward the results.

---

## 7. Filters

Several filters can be combined.

### Character scope

Choose between:

- **All characters**
- **Main narrative**
- **History / backstory**

The historical filter is useful because the novel contains extended genealogical and historical narratives that can otherwise make the map much denser.

### Family / branch

Filter the graph by major family or narrative branch, including:

- Komneni;
- Ibrahim / Xhavella;
- village / Tepelena;
- Voskopoja;
- Benishi / Bakri;
- Bilali;
- historical characters.

### Religion

Filter by:

- Christian;
- Muslim;
- Jewish;
- unspecified / other.

A character who changes religion can match both their original and later religion.

---

## 8. Selecting a character

Click or tap a character card to open the detail panel.

The selected character becomes the focus of the graph while unrelated characters are faded.

The side panel contains the character's available metadata and a list of their encoded relationships.

Relationship entries in the panel are themselves interactive: selecting another character from the list moves directly to that person.

---

## 9. Focus modes

When a character is selected, the **Highlight / Focus** control changes how much of their network remains emphasized.

### Immediate family
Shows the selected character and their direct relationships.

### Ancestors
Highlights the selected character's parental line and ancestors. A spouse/partner can also remain visible for context.

### Descendants
Highlights children, later descendants, and relevant spouse/partner context.

### All connections
Shows every character reachable through encoded relationships, including non-genealogical connections.

These modes are also available inside the character detail panel.

---

## 10. Find Connection

**Find Connection** answers the question:

> How are these two characters connected?

Click the connected-nodes icon and select two characters.

The application searches for the shortest meaningful path between them in three stages:

1. direct family relationships:
   - parent/child;
   - marriage;
   - partnership;
   - siblings;
2. wider kinship;
3. social/narrative relationships, only when a family/kinship route is not available.

The resulting path is displayed in words and highlighted directly on the graph, while unrelated characters fade.

For example, a path may be rendered conceptually as:

`Bilali → parent of → Fatimja → married to → Jani → child of → Ibrahimi`

The result also indicates whether it is:

- a **family / kinship path**, or
- a path that requires **narrative relationships**.

### Controls inside Find Connection

- choose the first character;
- choose the second character;
- **⇄** swaps the two;
- **Find Connection** calculates the path;
- **Clear Connection** removes the highlighted path;
- **Esc** closes the connection panel.

A connection can be calculated even if some of the characters in the path are currently outside the active visual filters.

---

## 11. Semantic zoom

The map changes the amount of information displayed on each card according to zoom level.

### Far zoom
Only major characters keep visible labels; minor characters remain present but visually quieter.

### Medium zoom
Cards display:

- flag;
- name;
- year.

### Close zoom
Cards display the full compact label:

- flag;
- name;
- year;
- religion or religion change.

This allows the same visualization to function both as an overview and as a detailed family map without permanently crowding the screen with text.

---

## 12. Hover inspection

On devices with a mouse or trackpad, hovering provides a temporary preview without changing the current selection.

### Hover over a character
The map temporarily emphasizes their immediate family/relationships and shows a tooltip with:

- name;
- year;
- religion or religion change.

### Hover over a relationship line
A tooltip explains:

- the relationship type;
- the characters connected by the line.

This is useful for checking whether a line actually belongs to a particular character in dense parts of the map.

Hover is only an enhancement. All essential information remains available through click/tap for touch devices.

---

## 13. Overview

The **Overview** button uses the framing icon and automatically fits the currently visible characters into the viewport.

It is useful after:

- zooming deeply into a branch;
- following several characters;
- searching;
- changing filters;
- exploring a connection.

---

## 14. Shareable links

The **Share** button uses the standard share icon and copies the current URL to the clipboard.

The URL stores the current state of the explorer, including:

- language;
- visualization mode;
- character scope;
- family branch filter;
- religion filter;
- focus mode;
- search query;
- selected character;
- active Find Connection path.

This means a shared link can open directly to a particular interpretation of the map instead of always returning to the default screen.

For example, a reader can share:

- a specific character;
- a filtered family branch;
- the Timeline view;
- a relationship path between two characters.

The state is stored in the URL hash, so no server-side session is required.

---

## 15. Export

The **Export** menu supports two formats.

### PNG
Exports the complete currently rendered graph as a high-resolution raster image.

Useful for:

- slides;
- quick sharing;
- documents;
- teaching materials.

### SVG
Exports a true vector representation of the graph.

Useful for:

- academic publications;
- posters;
- high-resolution printing;
- editing in vector-graphics software.

Active connection highlighting and faded context are preserved in the exported visualization.

Export filenames reflect the active view, for example:

`te-jetosh-ne-ishull-family.png`

or

`te-jetosh-ne-ishull-timeline.svg`

---

## 16. Reset / Clear

The **Clear / Reset** control returns the explorer to its default state:

- Albanian UI remains governed by the current language selector;
- Family Tree view;
- main narrative scope;
- all branches;
- all religions;
- immediate-family focus;
- empty search;
- no active character;
- no active Find Connection path.

---

# Multilingual interface

## 17. Languages

The interface is available in:

- 🇦🇱 **Albanian**
- 🇮🇹 **Italian**
- 🇬🇧 **English**

Changing language updates:

- title and subtitle;
- view names;
- search placeholder;
- filters;
- legend;
- buttons;
- relationship terminology;
- character metadata labels;
- Find Connection interface;
- place names and nationality labels where translations are available.

The underlying literary notes are currently primarily stored in Albanian. In the Italian and English interfaces they are therefore identified as notes from the Albanian source dataset rather than silently machine-translated.

---

# Data conventions

## 18. Chronology

Many dates in the novel are not stated directly.

The map therefore distinguishes between:

- explicitly known dates;
- reconstructed or estimated dates.

A reconstructed date is marked with **≈**.

The vertical layout should be read as a **chronological aid**, not as a claim that every character's birth year is historically exact.

---

## 19. Names and religious conversion

Some characters change name and/or religion during the novel.

The data model allows each character to store:

- main display name;
- aliases / previous names;
- religion at birth;
- later religion;
- approximate year of religious change.

The map intentionally keeps these transformations attached to a single person rather than creating separate nodes for the same character before and after conversion.

---

## 20. Historical and backstory characters

The novel contains characters who belong to:

- the main narrative;
- family history;
- historical digressions;
- political/religious backstory.

These are encoded separately through the **role/scope** system so that a reader can hide historical material when concentrating on the main narrative.

The map is a visualization of **the novel's character world and genealogical claims**. It should not automatically be treated as an independent historical database.

---

## 21. Source references and editions

Character notes can contain working references used while reconstructing the graph from the scanned PDF.

These references are useful for checking the source used during development, but **PDF page numbers are not treated as a navigation system** because:

- the scanned PDF pagination does not necessarily match the printed book;
- different editions can have different pagination.

For this reason there is intentionally **no page-number slider or edition-dependent reading-progress feature**.

---

# Technical information

## 22. Architecture

The project is intentionally lightweight.

The application is contained in a single:

`index.html`

It uses:

- HTML;
- CSS;
- vanilla JavaScript;
- **Cytoscape.js 3.28.1** for graph rendering and interaction.

Typography uses:

- Newsreader;
- IBM Plex Sans;
- IBM Plex Mono.

The fonts and Cytoscape library are loaded from external CDNs.

There is:

- no framework;
- no build process;
- no database server;
- no backend;
- no user account system.

All character and relationship data are currently embedded directly in `index.html`.

---

## 23. Data structure

Characters are stored in the `PEOPLE` collection.

A character can contain information such as:

```js
{
  id: "unique_id",
  name: "Character name",
  birthYear: 1750,
  birthplace: "place_key",
  religionOrigin: "christian",
  religionCurrent: "muslim",
  nationality: "nationality_key",
  flag: "🇦🇱",
  family: "Family name",
  role: "main",
  notes: "Notes from the novel",
  pages: "working source reference"
}
```

Optional fields support:

- approximate birth dates;
- death dates;
- aliases;
- religion-change dates;
- confidence/uncertainty.

Relationships are stored in `RELATIONS`.

Conceptually:

```js
{
  source: "character_a",
  target: "character_b",
  type: "parent"
}
```

Supported relationship types include:

- `parent`
- `spouse`
- `partner`
- `sibling`
- `kin`
- `social`

For `parent`, the direction is:

`source = parent → target = child`

---

## 24. Deterministic and dynamic layouts

The project deliberately uses different layout strategies for different questions.

### Family Tree
Uses manually controlled, deterministic positions designed for genealogical readability.

### Timeline
Uses a separate deterministic chronological layout.

### Relationship Network
Uses Cytoscape's force-directed COSE layout.

The Family Tree and Timeline positions are stored independently and restored whenever the user returns from the network view. This prevents the force-directed network from permanently changing the genealogical arrangement.

---

## 25. Responsive behavior

The interface adapts to smaller screens.

On mobile-width displays:

- the search bar expands to its own row;
- the side panel can occupy most of the screen width;
- long text labels on icon buttons are hidden while their icons remain visible;
- Find Connection controls become more compact;
- the statistics display is hidden to preserve space.

The graph remains zoomable and pannable through Cytoscape.

---

# Running the project

## 26. Local use

Because the project has no build step, the simplest option is to open:

`index.html`

in a modern browser.

An internet connection is currently required for the externally hosted:

- Cytoscape.js library;
- Google Fonts.

For development, using a small local HTTP server is recommended.

For example, with Python:

```bash
python -m http.server 8000
```

Then open:

`http://localhost:8000/`

---

## 27. GitHub Pages deployment

The repository is designed to work as a static GitHub Pages site.

After updating `index.html`:

1. commit the file;
2. push it to the branch used by GitHub Pages;
3. wait for GitHub Pages to redeploy;
4. open the live project and hard-refresh if a cached version is still visible.

No build command is required.

---

# Suggested use

The map can be used as:

- a reading companion after or during study of the novel;
- a genealogy reference;
- a way to investigate religious and naming transformations;
- a visualization of cross-family marriages;
- a tool for comparing narrative and historical networks;
- a teaching resource;
- a source of exportable diagrams for presentations or academic discussion.

A useful exploration workflow is:

1. begin in **Family Tree**;
2. select a character;
3. use **Ancestors** or **Descendants**;
4. use **Find Connection** when two people seem distantly related;
5. switch to **Relationship Network** to inspect non-family links;
6. use **Share** to preserve the current state;
7. use **SVG Export** when a publication-quality diagram is needed.

---

## Project status

The current interface and core interaction model are feature-complete for the present dataset.

Future work can concentrate on:

- correcting or expanding character data;
- improving uncertain genealogical relationships;
- adding newly identified minor characters;
- refining translations of literary notes;
- verifying chronology against other editions without tying the interface to edition-specific page numbers.

---

## Acknowledgement

This is an independent interactive visualization based on the characters and relationships in Ben Blushi's **_Të jetosh në ishull_**. The application does not reproduce the full text of the novel.
