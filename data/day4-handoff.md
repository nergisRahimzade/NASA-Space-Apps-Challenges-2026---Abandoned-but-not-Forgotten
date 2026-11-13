# Day 4: seven objects for the story

Ticket: ANF-D04-DAT

Sources checked: 2026-11-10

## Delivery and selection

`missions.json` now contains the seven objects proposed by the teammate and accepted by the data owner: three Moon objects (`surveyor-3`, `eagle-descent-stage`, `lunar-rover`) and four Mars objects (`viking-1`, `sojourner`, `spirit`, `opportunity`). Existing IDs, field names and array structure are preserved. The other five candidates remain in [the research pool](candidates.md).

This set spans a robotic lunar precursor, a crewed landing, lunar mobility, a stationary Mars laboratory and successive Mars rovers. It is the Day 4 story selection; model availability has not yet been established and remains Day 5 work.

The starting data and schema came from the teammate's [ANF-D01-BE commit de5d946](https://github.com/nergisRahimzade/NASA-Space-Apps-Challenges-2026---Abandoned-but-not-Forgotten/tree/de5d946a421ad3d9742f40e4855796eb9073ad74/data). Only those two data files were carried forward; that branch's website files were not imported. This PR builds on Day 3 [PR #4](https://github.com/nergisRahimzade/NASA-Space-Apps-Challenges-2026---Abandoned-but-not-Forgotten/pull/4), which was still open when Day 4 was prepared. Merge #4 first. Day 4 also targets `main`, so its diff includes Day 3 until then. The BE branch has overlapping versions of these files: coordinate its later merge so it does not restore the placeholder data or old schema.

## Data contract and frontend behavior

- Keep all 16 existing fields present. Stable `id` and `name` values identify each record; `verified` is always a boolean and `sources` is always a URL list. Unknown descriptive values and coordinates use `null`; no sources uses `[]`.
- The inherited schema allowed `null` only for coordinates despite describing a wider null policy. The updated schema makes descriptive fields and `modelFile` nullable and requires the previously optional existing fields as well. No field is renamed. It adds calendar-date format validation; consumers must enable date/URI format checks (for Ajv, use registered formats). A conditional prevents `verified: true` when one of the five historical fields, date context or source evidence is missing. A null model or story does not prevent factual verification. The teammate's branch still had its original schema when checked on 2026-11-10; this PR includes the agreed changes for review without editing her branch.
- `date` identifies `dateEvent`, not abandonment. Apollo 15 keeps **1971-07-31, first deployment/use**; the rover arrived aboard Falcon on July 30. The separate launch dates remain in [Moon](moon-day3.md) and [Mars](mars-day3.md) research because the agreed application contract has no launch-date field.
- All markers are **landing or arrival references**, not final rover positions. Display the supplied location text. The Apollo 15 location explicitly identifies arrival aboard Falcon; Sojourner identifies arrival aboard Pathfinder.
- `coordinates: null` means **do not plot a marker**. Show that coordinates are unavailable while retaining the known location name; do not convert null to `(0, 0)`. Known coordinate values use signed north/east degrees; longitudes over 180 E are wrapped by subtracting 360. This does not change the underlying reference frame.
- All seven `modelFile` values are **null**: the checked BE branch contains no model files. Use a placeholder shape, such as the planned cube and do not request a guessed GLB. Once available, use `models/<id>.glb`, relative to `public/`; the browser URL needs a leading `/`. Day 5 will record model file sizes and licenses in `models.md`, separately from historical-fact verification.
- The teammate confirmed on **2026-11-10** that `verified` covers **date, location, coordinates, goal and payload checked against sources**, not model availability. Six records are **true** after that review; **Surveyor 3 remains false** because its map coordinates are unresolved. `dateEvent` supplies the date context. Source verification does not certify a common coordinate frame, resolve every source alternative or identify final rover positions. Schema validation cannot establish factual truth by itself.
- Payload text describes historical equipment, not a complete present-day inventory. Surveyor 3's returned parts and Eagle's surviving descent stage are distinguished explicitly. Every story is at most 60 whitespace-delimited words.

## Coordinates and source choices

Use these values for contextual landing-site maps. Their displayed precision is inherited from sources, not a claim that all objects share a survey frame or uncertainty. The compact schema has no frame field: retain this table with the dataset, and agree a metadata extension before precision overlays or distance calculations. A single Earth WGS84 label would be incorrect.

| ID | Adopted latitude, longitude | Primary coordinate source and interpretation |
| --- | --- | --- |
| `surveyor-3` | `null` | [NSSDCA summary](https://nssdc.gsfc.nasa.gov/planetary/lunar/surveyor.html) gives `(-3.01, -23.34)` while [NASA's narrative](https://science.nasa.gov/mission/surveyor-3/) gives `(-3, -23.41)`. These summary sources do not establish a common frame or a reconciled position. Preserve the conflict instead of assigning a precise pin. |
| `eagle-descent-stage` | `0.67416, 23.47314` | [NSSDCA LRO-derived table](https://nssdc.gsfc.nasa.gov/planetary/lunar/lunar_sites.html), Apollo 11 **Lunar Module** row, not reflector. Planetocentric Mean Earth/Polar Axis lunar system, DE421. |
| `lunar-rover` | `26.13239, 3.63330` | Same [table](https://nssdc.gsfc.nasa.gov/planetary/lunar/lunar_sites.html), Apollo 15 **Lunar Module** row. Falcon arrival reference only; same DE421 convention. Final rover parking coordinates remain unverified. |
| `viking-1` | `22.27, -47.95` | [NSSDCA Viking](https://nssdc.gsfc.nasa.gov/planetary/viking.html), explicitly planetocentric; `312.05 E - 360 = -47.95`. NASA's other narrative value remains in [Day 3 notes](mars-day3.md). |
| `sojourner` | `19.33, -33.55` | [NSSDCA Pathfinder](https://nssdc.gsfc.nasa.gov/planetary/mesur.html), Pathfinder landing site; reference frame not stated. This is not Sojourner's final location. |
| `spirit` | `-14.572, 175.478` | [NSSDCA mission catalog](https://nssdc.gsfc.nasa.gov/nmc/spacecraft/display.action?id=2003-027A), landing in Gusev; frame not stated. Selected catalog location is an approximate mission landing reference. |
| `opportunity` | `-1.946, -5.527` | [NSSDCA mission catalog](https://nssdc.gsfc.nasa.gov/nmc/spacecraft/display.action?id=2003-032A), IAU 2000 body-centered coordinates; `354.473 E - 360 = -5.527`. Eagle crater landing reference. |

Day 3 used NASA Science overview coordinates for Spirit `(-14.5692, 175.4729)` and Opportunity `(-1.9483, -5.52583)`. Day 4 uses the newly checked, mission-specific NSSDCA catalog entries requested by the teammate. These alternatives are preserved here; no averaging, frame equivalence or higher accuracy is claimed. Surveyor 3 lacks an equivalent resolved mission-specific choice in this review and remains null. Historical research files are left unchanged.

## Fact review by record

Each object's `sources` list includes its factual and coordinate evidence. The following shows what was checked and which draft wording changed.

| ID | Evidence and checks |
| --- | --- |
| `surveyor-3` | NASA mission supports camera, scoop, soil investigation and the Apollo 12 recovery; NSSDCA supports the UTC landing date. The displayed object is the **remaining structure**; returned camera/scoop are not still aboard. Coordinate discrepancy remains open. |
| `eagle-descent-stage` | NSSDCA mission facts support landing date; NASA's lunar-module technical introduction supports original descent-stage equipment; NASA LRO imagery supports the remaining stage and tracks. Do not attach nearby deployed experiments to the stage's present inventory. |
| `lunar-rover` | NASA Marshall history supports July 31 deployment; NSSDCA LRV description supports equipment, folding against the lander's exterior bay and 27.8 km travel. NASA's summary uses 27.9 km; the text says **about 28 km**. Replaced the draft's misleading “inside the lander.” |
| `viking-1` | NASA mission supports instruments, nonoperating seismometer and more than six years of operation; NSSDCA supports landing and the inconclusive life search. Removed “thousands of pictures” to avoid conflating image totals for both Viking landers. Final-contact day differs between sources, so status uses the agreed year only. |
| `sojourner` | NSSDCA Pathfinder supports arrival and 1997 communication loss; NASA PDS supports the rover's three cameras and APXS. NASA mission identifies the first NASA Mars rover. Removed the loose “7 days” duration claim rather than confusing Earth days and Martian sols. |
| `spirit` | NSSDCA mission catalog supports its landing reference and 2010 last contact; NASA mission supports instruments, water-investigation goal and more than six years of exploration. NASA MER resource explicitly confirms the January 4 UTC landing date. |
| `opportunity` | NSSDCA mission catalog supports landing reference and 2018 last contact; NASA mission supports instruments, water-investigation goal, almost fifteen years and roughly 45 km travel. NASA MER resource explicitly confirms January 25 UTC. No current distance-record claim is made. |

## Validation

Validation results are recorded in [day4-validation.json](day4-validation.json). Schema validity is distinct from scientific review: JSON Schema cannot determine whether a source supports a statement or a model actually exists. Checks include the selected IDs, all 16 keys, the 3/4 body split, date formats, source URLs, coordinate bounds, story length and fact-only verification flags, plus positive and negative probes for nulls, omitted fields, malformed dates and coordinates. In particular, a verified record with a null model is valid, while a verified record with an unknown historical field is invalid.

Website lint and typecheck passed. The production build remains unverified: the initial attempt could not fetch Google Fonts; an approved network retry then hit a local process/port permission error in Turbopack. Details are in the validation record. These data changes do not implement the frontend's fallback behavior; the frontend owner must connect the agreed null states when consuming them.
