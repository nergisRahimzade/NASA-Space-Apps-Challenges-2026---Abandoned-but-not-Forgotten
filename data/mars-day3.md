# Day 3 research: Mars candidates

Ticket: ANF-D03-DAT

Sources checked: 2026-11-07

Scope: six candidates from Day 2; research notes, not the final application schema or Day 4 selection.

## Reading these records

- Dates are ISO calendar dates in UTC. Where the source uses UT, that label is retained in the evidence note. No subsecond UT/UTC equivalence is asserted.
- Coordinates are degrees, with the source's N/S and E/W notation preserved. They identify a **landing site**, not a rover's final position. A longitude conversion does not establish a latitude reference system.
- `not stated` means the cited source does not specify the coordinate frame; it does not mean the coordinate is zero or verified in a particular frame. Preserve this limitation when building the map.
- Payloads describe equipment carried during the mission, not a verified inventory of intact equipment today. Orbiter and aeroshell instruments are excluded from lander payloads.

## Viking 1 lander

| Field | Research value and evidence |
| --- | --- |
| Launch date | **1975-08-20**, aboard the combined orbiter/lander spacecraft. NASA records 21:22 UT. [NASA Viking 1: launch table][viking1] |
| Landing date | **1976-07-20**. [NSSDCA Viking project][viking] |
| Landing site | Chryse Planitia; **22.27° N, 312.05° E**, explicitly **planetocentric**. [NSSDCA Viking project][viking] |
| Goal | Investigate the surface and atmosphere and test soil for evidence of life. [NSSDCA Viking project][viking] |
| Lander payload | Two surface cameras; GCMS chemical analyzer; biology experiments; X-ray fluorescence instrument; weather sensors; seismometer; sampling arm. [NASA Viking 1: lander instrument list][viking1] |
| Quality flags | NASA's mission history instead gives **22.483° N, 47.94° W**, without naming its latitude system. Keep that alternative separate; do not average it with NSSDCA's planetocentric value. The carried seismometer did not operate. [NASA Viking 1][viking1] |

## Viking 2 lander

| Field | Research value and evidence |
| --- | --- |
| Launch date | **1975-09-09**, aboard the combined orbiter/lander spacecraft. NASA records 18:39 UT. [NASA Viking 2: launch table][viking2] |
| Landing date | **1976-09-03**. [NSSDCA Viking project][viking] |
| Landing site | Utopia Planitia; **47.64° N, 134.29° E**, explicitly **planetocentric**. [NSSDCA Viking project][viking] |
| Goal | Examine soil, atmosphere and weather at a second landing site, including experiments seeking evidence of life. [NSSDCA Viking project][viking] |
| Lander payload | Surface camera pair; biology experiments; GCMS and X-ray fluorescence instruments; meteorology sensors; seismometer; arm for collecting samples. [NASA Viking 2: lander instrument list][viking2] |
| Quality flags | NASA's mission history gives **47.968° N, 225.71° W**, with latitude system not stated. Keep separate from the explicit planetocentric coordinates above. [NASA Viking 2][viking2] |

The Viking sources also differ on cessation-of-communication dates. NSSDCA lists 1982-11-13 / 1980-04-11 for Viking 1 / 2; NASA mission pages list 1982-11-11 / 1980-04-12. These remain unresolved if mission-end fields are added; they do not affect the launch or landing dates above. [NSSDCA][viking], [NASA Viking 1][viking1], [NASA Viking 2][viking2]

## Sojourner rover

| Field | Research value and evidence |
| --- | --- |
| Launch date | **1996-12-04**, carried by Mars Pathfinder; NSSDCA records 06:58 UT. [NSSDCA Pathfinder project][pathfinder] |
| Landing date | **1997-07-04**, arrival aboard Pathfinder, not rover rollout. [NSSDCA Pathfinder project][pathfinder] |
| Landing site | Ares Vallis; **19.33° N, 33.55° W**, the reported **Pathfinder landing site**. Latitude system and reference frame: **not stated** in this source. [NSSDCA Pathfinder project][pathfinder] |
| Goal | Demonstrate mobile exploration, obtain close-up terrain images, and analyze rocks and soil at multiple locations. [NASA PDS rover-camera documentation][sojourner-pds] |
| Rover payload | Alpha Proton X-ray Spectrometer (APXS); three cameras: two forward monochrome cameras with ranging lasers and one rear camera for color/spectral images. [NASA PDS rover-camera documentation][sojourner-pds] |
| Quality flags | Exact final rover coordinates: **not verified in this research**. Do not label Pathfinder's site coordinates as Sojourner's final position. The lander's atmospheric instruments and Imager for Mars Pathfinder are not rover payloads. Rollout was **1997-07-06 around 05:40 UT**, a distinct event. [PDS][sojourner-pds], [NSSDCA][pathfinder] |

## Spirit rover (MER-A)

| Field | Research value and evidence |
| --- | --- |
| Launch date | **2003-06-10**; NASA explicitly records 17:58:47 UTC in the mission narrative. [NASA Spirit][spirit] |
| Landing date | **2004-01-04 UTC**, equivalent to January 3 PST. [NASA MER date clarification][mer-dates] |
| Landing site | Gusev crater / Columbia Memorial Station; **14.5692° S, 175.4729° E**. Latitude system and reference frame: **not stated** on the cited page. [NASA Spirit][spirit] |
| Goal | Study rocks and soils for evidence of past water and conditions relevant to habitability. [NASA Spirit][spirit] |
| Rover payload | Pancam, Mini-TES, Mössbauer spectrometer, APXS, Microscopic Imager, Rock Abrasion Tool and magnetic dust experiments; Navcam supports navigation. [NASA MER instruments][mer-instruments], [NASA Spirit][spirit] |
| Quality flags | These are landing coordinates, **not final rover coordinates**. Spirit subsequently traveled 7.73 km; the precise final position has not been verified here. Preserve the UTC/PST date distinction. [NASA Spirit][spirit], [NASA MER date clarification][mer-dates] |

## Opportunity rover (MER-B)

| Field | Research value and evidence |
| --- | --- |
| Launch date | **2003-07-08 UTC**. Explicit conversion: July 7 at 20:18:15 PDT + 7 hours = July 8 at 03:18:15 UTC. NASA/JPL's contemporary report gives the corresponding 23:18:15 EDT liftoff. [NASA Opportunity][opportunity], [JPL launch report][opportunity-launch] |
| Landing date | **2004-01-25 UTC**, equivalent to January 24 PST. [NASA MER date clarification][mer-dates] |
| Landing site | Eagle crater, Meridiani Planum / Challenger Memorial Station; **1.9483° S, 354.47417° E**. Latitude system and reference frame: **not stated** on the cited page. [NASA Opportunity][opportunity] |
| Goal | Use local geology and rock/soil chemistry to reconstruct past water activity and potentially habitable environments. [JPL launch report][opportunity-launch] |
| Rover payload | Same MER science suite as Spirit: Pancam, Mini-TES, Mössbauer, APXS, Microscopic Imager, abrasion tool and magnets, with navigation cameras. [NASA MER instruments][mer-instruments], [NASA Opportunity][opportunity] |
| Quality flags | The frequently shown **July 7 launch date is a U.S. local date**. Landing coordinates are **not** the rover's eventual Perseverance Valley location; exact final coordinates remain unverified here. The NASA narrative's landing clock times are internally inconsistent (21:05 PST versus 04:54 UTC); no precise touchdown time is adopted. [NASA Opportunity][opportunity] |

## Phoenix Mars lander

| Field | Research value and evidence |
| --- | --- |
| Launch date | **2007-08-04 UTC**. [NASA Phoenix: Quick Facts][phoenix] |
| Landing date | **2008-05-25**. [NASA Phoenix][phoenix] |
| Landing site | Arctic plains of Vastitas Borealis; approximately **68.22° N, 234.25° E**. Latitude system and reference frame: **not stated** in the mission overview. [NASA Phoenix: panorama caption][phoenix] |
| Goal | Investigate Arctic water history, soil chemistry and organic molecules to assess past habitability. [NASA Phoenix][phoenix] |
| Lander payload | Stereo imager (SSI), robotic-arm camera (RAC), MECA microscopy/chemistry package, TEGA heated-sample gas analysis, meteorology station (MET), and the sample-collecting robotic arm. This is the overview's instrument summary, not a complete engineering inventory. [NASA Phoenix][phoenix] |
| Quality flags | Coordinates are rounded overview values, not a claim of survey precision. A frame-qualified coordinate source is required before precise map placement. Do not describe the habitability investigation as a confirmed discovery of life. |

## Follow-up before application use

1. The data owner confirmed **landing sites, clearly labelled**, on 2026-11-07. The front-end/map owner should implement that label. Final hardware positions remain outside the initial map scope and would require additional research for all three Mars rovers.
2. Keep `latitudeType` / reference frame and `coordinateSource` alongside any numeric coordinates. Only the selected Viking values have an explicit latitude type in this research; do not silently mark the others as planetocentric or Earth WGS84.
3. Use separate launch, landing, rollout, last-contact and mission-end fields. Keep raw source labels when deriving a UTC date.
4. Day 4 chooses the final objects and schema with the team; Day 5 checks model availability, size and usage terms.

[viking1]: https://science.nasa.gov/mission/viking-1/
[viking2]: https://science.nasa.gov/mission/viking-2/
[viking]: https://nssdc.gsfc.nasa.gov/planetary/viking.html
[pathfinder]: https://nssdc.gsfc.nasa.gov/planetary/mesur.html
[sojourner-pds]: https://pds.nasa.gov/data/mpfr-m-apxs-2-edr-v1.0/mprv_0001/document/rcinst.htm
[spirit]: https://science.nasa.gov/mission/mer-spirit/
[opportunity]: https://science.nasa.gov/mission/mer-opportunity/
[opportunity-launch]: https://www.jpl.nasa.gov/news/newly-launched-opportunity-follows-mars-bound-spirit/
[mer-dates]: https://science.nasa.gov/3d-resources/mars-exploration-rover-spirit-and-opportunity/
[mer-instruments]: https://science.nasa.gov/mission/mars-exploration-rovers-spirit-and-opportunity/science-instruments/
[phoenix]: https://science.nasa.gov/mission/mars-phoenix/
