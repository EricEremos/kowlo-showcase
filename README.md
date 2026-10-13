# KOWLO

**Hong Kong, in your colours.**

Your photographs remember moments. KOWLO connects them to places: a personal Hong Kong atlas coloured by the photos you take, with notes you can revisit and records you can keep.

**Built by Hyunjun Kim · Independent product design & AI-assisted development · Started September 2026**

[See the product journey ↓](#the-product-journey)

## The product journey

<p>
  <img src="assets/app-atlas-night.jpg" width="240" alt="KOWLO night atlas after importing sample photos, showing eight of Hong Kong's eighteen districts coloured in.">
  <img src="assets/app-district.jpg" width="240" alt="Yau Tsim Mong district screen with a tile wall and one recorded place, Tsim Sha Tsui.">
  <img src="assets/app-place.jpg" width="240" alt="Tsim Sha Tsui place record with photo-derived colours, a capture date and an editable journal note.">
</p>

*Actual browser-app captures from the September 2026 interface. Eight synthetic sample photos supply the demonstration data; the places, dates and notes are illustrative. These screens show an earlier product version.*

1. **See your city take shape.** Import photos with GPS data. Their locations and optional colours add detail to your atlas.
2. **Follow your own line.** Hong Kong's **18 districts** become stations; recorded places become exits. Open a district to find its memories.
3. **Keep the story behind a place.** Revisit its date, colours and personal note. The local journal supports offline access after initial preparation and record export.

## What I built and why

- **Product direction and navigation:** shaped the photo-to-journal journey and designed the atlas, district and place views in Figma. The station/exit hierarchy gives a growing collection a structure people can browse.
- **Photo and geographic data workflows:** connected on-device GPS and colour extraction to district grouping and the visual atlas. Preserved original coordinates separately from decorative tiles and nearby-name suggestions, so the interface does not turn a suggestion into a confirmed visit.
- **A journal people can keep:** developed local storage, note editing, record management and export. Offline access after preparation lets people revisit saved records without a connection; exports give them a reusable copy of their data.
- **Design through implementation:** used AI-assisted development to turn the product flows into working behaviour, connected Day/Night appearance to the atlas colour system, and compared the real interface with its Figma direction.

## Engineering behind the experience

The local application uses **JavaScript modules, IndexedDB and an offline web shell**. The project also includes **Swift/Kotlin native wrappers** and a separately tested **PostgreSQL/PostGIS** data foundation.

Retained development checks include:

- **684 geographic controls:** browser and PostGIS district classification agreed on the recorded cases; the accompanying migration/database unit passed **209 checks**.
- **200 generated journal snapshots:** export checks exercised preservation of coordinates, notes, IDs and capture-time states. Browser checks also exercised actual downloads while offline.

These are historical engineering checks, with their scope explained in [the evidence notes](docs/engineering-evidence.md). They measure implementation behaviour, not user adoption or commercial impact.

<details>
<summary><strong>Explore the visual direction</strong></summary>

![Illustrative KOWLO concept cover: Hong Kong drawn as a personal memory print.](assets/portfolio-cover.png)

The cover expresses the original memory-print concept. [View the retained Figma/application comparison](assets/interface-evidence.jpg) for the September Day/Night direction, including import and record-management states.

</details>

## Current status

Development and maintenance paused on **12 October 2026**. The project has a historical browser beta and retained local implementation evidence. Hosted private sync remains unfinished, and physical-device acceptance is not established. Adoption and retention have not been measured.

This public repository presents the product and my contribution. Application source and development history are kept in a separate private repository.

---

**Hyunjun Kim** · [LinkedIn](https://linkedin.com/in/ericmos) · [GitHub](https://github.com/EricEremos) · [Credits & reuse terms](CREDITS.md)
