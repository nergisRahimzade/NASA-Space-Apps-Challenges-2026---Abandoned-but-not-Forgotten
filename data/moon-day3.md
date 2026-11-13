# Day 3 research: Moon candidates

Ticket: ANF-D03-DAT

Sources checked: 2026-11-07

Status: research notes for all six Day 2 Moon candidates; not the Day 4 selection or application schema.

## Reading these records

- Launch is the launch from Earth of the carrying mission. An Apollo rover or descent stage did not launch separately.
- Dates below use the universal-time calendar date given by the source (UT/GMT in historical records). Landing, rover deployment and mission end are separate events.
- Coordinates are degrees, latitude first. Signed values use north/east positive and south/west negative, with longitude in -180 to 180. Changing 316.79 E to -43.21 is only longitude wrapping, not a reference-frame transformation.
- Apollo LM coordinates below use NSSDCA's LRO-derived, planetocentric Mean Earth/Polar Axis lunar system with DE421. The linked table does **not** supply rover parking positions. Its printed digits are retained for traceability, not an assertion of measurement accuracy. [Coordinate definition and table](https://nssdc.gsfc.nasa.gov/planetary/lunar/lunar_sites.html)
- Payload lists describe original scientific equipment or operational equipment, not a verified inventory of everything still attached today. Deployed surface experiments are distinct objects from the descent stage that transported them.

## Surveyor 1 lander

| Field | Research value and evidence |
| --- | --- |
| Launch date | **1966-05-30**, listed at 14:41:01 UT. [NASA mission, launch table](https://science.nasa.gov/mission/surveyor-1/) |
| Landing date | **1966-06-02**. [NSSDCA Surveyor summary](https://nssdc.gsfc.nasa.gov/planetary/lunar/surveyor.html) |
| Landing coordinates | NSSDCA reports **2.45 S, 316.79 E** → **(-2.45, -43.21)**, Flamsteed P. [NSSDCA summary](https://nssdc.gsfc.nasa.gov/planetary/lunar/surveyor.html) |
| Goal | Demonstrate controlled lunar landing and surface operation; image and assess terrain in preparation for crewed landings. [NASA mission](https://science.nasa.gov/mission/surveyor-1/), [NSSDCA program objectives](https://nssdc.gsfc.nasa.gov/planetary/lunar/surveyor.html) |
| Original payload | Television camera. Landing-pad strain gauges supplied engineering measurements; these are not an additional chemical-analysis payload. [NASA mission, instruments and engineering description](https://science.nasa.gov/mission/surveyor-1/) |
| Open issue | NASA's mission narrative instead reports **2.46 S, 43.32 W** → **(-2.46, -43.32)** as the announced touchdown position. The two sources do not identify a common reference frame or explain the difference. Preserve both; an exact display pin needs reconciliation. [NASA mission](https://science.nasa.gov/mission/surveyor-1/) |

## Surveyor 3 lander: remaining structure

| Field | Research value and evidence |
| --- | --- |
| Launch date | **1967-04-17**, listed at 07:05:01 UT. [NASA mission, launch table](https://science.nasa.gov/mission/surveyor-3/) |
| Landing date | **1967-04-20**. [NSSDCA Surveyor summary](https://nssdc.gsfc.nasa.gov/planetary/lunar/surveyor.html) |
| Landing coordinates | NSSDCA reports **3.01 S, 336.66 E** → **(-3.01, -23.34)**, Oceanus Procellarum. [NSSDCA summary](https://nssdc.gsfc.nasa.gov/planetary/lunar/surveyor.html) |
| Goal | Test lunar landing and investigate surface bearing properties through imaging and soil-mechanics experiments. [NASA mission](https://science.nasa.gov/mission/surveyor-3/) |
| Original payload | Television camera and surface sampler. Apollo 12 recovered the camera system, soil scoop and other parts; those returned parts must not be presented as hardware still on the Moon. [NASA mission, instruments and recovery account](https://science.nasa.gov/mission/surveyor-3/) |
| Open issues | NASA's mission narrative gives **3 S, 23.41 W** → **(-3, -23.41)**, unlike NSSDCA. Frame/epoch not established for either summary. Landing time also differs: NASA **00:04:17 UT** versus NSSDCA **00:04:53 UT**. Keep the agreed date only for presentation until seconds and position are reconciled. Exact present-day attached-part inventory remains unverified. [NASA mission](https://science.nasa.gov/mission/surveyor-3/), [NSSDCA summary](https://nssdc.gsfc.nasa.gov/planetary/lunar/surveyor.html) |

## Apollo 11 Eagle descent stage

| Field | Research value and evidence |
| --- | --- |
| Launch date | **1969-07-16**, aboard Apollo 11; listed at 13:32:00 UT. [NSSDCA mission facts](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo11info.html) |
| Landing date | **1969-07-20**. [NSSDCA mission facts](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo11info.html) |
| Landing coordinates | **(0.67416, 23.47314)**, LM site at Tranquility Base; use the Lunar Module row, not the nearby reflector row. [NSSDCA precise coordinates](https://nssdc.gsfc.nasa.gov/planetary/lunar/lunar_sites.html) |
| Goal | Support the first crewed lunar landing and safe return, with surface sampling, photography and experiment deployment. [NASA mission overview, objectives](https://www.nasa.gov/missions/apollo/apollo-11/apollo-11-mission-overview/) |
| Original mission surface payload | Television camera, passive seismic package, laser reflector and solar-wind composition experiment, plus sample-collection equipment. These were surface activities/equipment delivered by the mission, not all instruments permanently attached to the surviving stage. [NASA mission overview](https://www.nasa.gov/missions/apollo/apollo-11/apollo-11-mission-overview/), [NSSDCA experiment list](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo11info.html) |
| Scope / gap | Candidate is only Eagle's **descent stage**, not its ascent stage, crew or nearby instruments. A complete present-day inventory of attached equipment is not established by these mission summaries. |

## Apollo 12 Intrepid descent stage

| Field | Research value and evidence |
| --- | --- |
| Launch date | **1969-11-14**, aboard Apollo 12; listed at 16:22:00 UT. [NSSDCA mission facts](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo12info.html) |
| Landing date | **1969-11-19**. [NSSDCA mission facts](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo12info.html) |
| Landing coordinates | **(-3.0128, -23.4219)**, LM site in Oceanus Procellarum. [NSSDCA precise coordinates](https://nssdc.gsfc.nasa.gov/planetary/lunar/lunar_sites.html) |
| Goal | Demonstrate precision landing, investigate and sample the site, deploy long-duration experiments, and recover Surveyor 3 components. [NASA objectives](https://www.nasa.gov/missions/apollo/apollo-12-the-pinpoint-mission/) |
| Original mission surface payload | ALSEP instruments included passive seismic, solar-wind spectrometer, lunar surface magnetometer, suprathermal-ion detector and cold-cathode ion gauge; the mission also carried photography and sampling equipment. [NSSDCA LM experiment list](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo12info.html) |
| Scope / gap | These experiments were deployed separately from Intrepid. Candidate is the **descent stage**, not the ALSEP station or ascent-stage impact site. Complete remaining attached-part inventory is unverified. [NASA objectives and deployment account](https://www.nasa.gov/missions/apollo/apollo-12-the-pinpoint-mission/) |

## Apollo 15 Lunar Roving Vehicle

| Field | Research value and evidence |
| --- | --- |
| Launch date | **1971-07-26**, aboard Apollo 15; listed at 13:34:00 UT. [NSSDCA mission facts](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo15info.html) |
| Arrival / landing date | **1971-07-30**, carried by LM Falcon. The Day 2 candidate date, **1971-07-31**, labels first deployment/use, not landing. [NSSDCA landing date](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo15info.html), [NASA deployment history](https://www.nasa.gov/centers-and-facilities/marshall/the-marshall-star-288/) |
| Landing-site reference | **(26.13239, 3.63330)**, **Falcon's** location at Hadley-Apennine. This is not the rover's final parking position. [NSSDCA LM coordinates](https://nssdc.gsfc.nasa.gov/planetary/lunar/lunar_sites.html) |
| Goal | Extend astronauts' surface exploration range beyond walking distance. [NSSDCA LRV overview](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo_lrv.html) |
| Original operational payload / equipment | Two crew seats, a communications relay unit and television camera; these support crew mobility and communication rather than constituting the whole Apollo 15 science package. [NSSDCA LRV description](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo_lrv.html) |
| Open issues | Final parking latitude/longitude and a complete mission-specific cargo/remaining-equipment inventory are **not verified** here. Do not copy Falcon's coordinates into a field named current rover position. |

## Apollo 17 Lunar Roving Vehicle

| Field | Research value and evidence |
| --- | --- |
| Launch date | **1972-12-07**, aboard Apollo 17; listed at 05:33:00 UT. [NSSDCA mission facts](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo17info.html) |
| Arrival / landing date | **1972-12-11**, carried by LM Challenger. [NSSDCA mission facts](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo17info.html) |
| Landing-site reference | **(20.1911, 30.7723)**, **Challenger's** location at Taurus-Littrow. This is not the rover's final parking position. [NSSDCA LM coordinates](https://nssdc.gsfc.nasa.gov/planetary/lunar/lunar_sites.html) |
| Goal | Extend crew traverses for geological observation, sampling and surface experiments in Taurus-Littrow. [NASA mission objectives](https://www.nasa.gov/wp-content/uploads/static/history/SP-4029/Apollo_17a_Summary.htm), [NSSDCA LRV overview](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo_lrv.html) |
| Original operational payload / equipment | Crew seating, communications relay and TV camera; mission-specific rover instruments included the traverse gravimeter and the **receiver** of the Surface Electrical Properties experiment. Its transmitter was placed near the LM. [NSSDCA LRV overview](https://nssdc.gsfc.nasa.gov/planetary/lunar/apollo_lrv.html), [NASA-hosted experiment descriptions](https://history.nasa.gov/wp-content/uploads/static/history/alsj/HamishALSEP.html) |
| Open issues | Final parking coordinates and complete remaining-equipment inventory are **not verified** here. The SEP recorder was removed before departure, so historical instrument carriage is not evidence that all parts remain aboard. [NASA surface-phase account](https://www.nasa.gov/wp-content/uploads/static/history/SP-4029/Apollo_17a_Summary.htm) |

## Decisions for the team before application data is finalized

1. The data owner confirmed **landing-site references, clearly labelled**, on 2026-11-07. Apollo rover markers must say “Arrival site aboard the lunar module”, not final parking position. Separate final-position fields would be needed if that scope is added later.
2. Preserve `object` versus `parent mission` and `original payload` versus `remaining hardware` in the agreed data structure. This avoids assigning an entire Apollo science package to a surviving descent stage.
3. Reconcile the two Surveyor position pairs before precise mapping. No source-derived uncertainty radius or common reference frame was identified; do not invent either.
4. Select the final 5–8 Moon/Mars candidates together on Day 4. These research gaps are not grounds for silently dropping a candidate or expanding to model research early.
