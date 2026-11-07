# Day 3: candidate fact research

Ticket: ANF-D03-DAT

Sources checked: 2026-11-07

Status: research handoff; final selection and application schema pending team agreement.

## Deliverables

All 12 Day 2 candidates are retained. The records below cover Earth launch dates, landing coordinates, goals and payloads, with field-level primary sources and explicit uncertainty notes.

- [Moon: six candidate records](moon-day3.md)
- [Mars: six candidate records](mars-day3.md)
- [Original Day 2 candidate list](candidates.md)

The Day 2 list is preserved as a historical research baseline. Its source-check date and next-step wording are unchanged; this file records the Day 3 work.

## How to use these facts

- **Launch** means launch from Earth, including launch aboard a parent mission for a rover or lunar-module component. It does not mean rover deployment, lunar ascent or the date an object became inactive.
- **Landing coordinates** identify the sourced landing site. For an Apollo rover, the parent lunar-module landing site is only a reference for arrival; it is not the rover's final parking position. Mars rovers also moved after landing.
- **Coordinate conventions** travel with the values. Preserve latitude type, longitude direction/range and reference frame where the source provides them. A source that does not specify a frame remains explicitly unspecified. Changing west to east longitude does not convert latitude type or reference frame.
- **Goals and payloads** distinguish the physical candidate from its parent mission. Instruments deployed nearby, hardware returned to Earth and orbiter instruments are not automatically equipment still attached to the candidate.
- **Unverified** means missing from the sources checked, not that the fact is unknowable or the object lacks the equipment. Differences between sources remain visible rather than being averaged.
- Instrument summaries describe the historical mission configuration. They are not a verified present-day inventory or a claim that the equipment still works.

These Markdown records are research inputs, not a production `missions.json` contract. Do not treat any landing-site value as a verified current-location marker.

## Confirmed map decision

On 2026-11-07, the data owner selected **landing sites, clearly labelled** for the initial website markers. Use “Landing site” for landers and Mars rover arrivals; use “Arrival site aboard the lunar module” for the Apollo rovers. Do not describe these as final parking or current rover positions. This selects the meaning of a marker, not a resolution of source-coordinate conflicts.

## Team decisions for Day 4

| Decision | Proposed starting point | Who should confirm |
| --- | --- | --- |
| Shared integration branch | Target `main` using the agreed Earth System workflow; restore Day 2 research in the same PR. | Teammate review before merge |
| Map implementation | Implement the confirmed landing-site labels above and preserve source/frame caveats. Final-resting-place mapping is outside the initial scope. | Frontend + design |
| Final candidates | Select 5–8 from the existing 12 after comparing the story, evidence and asset feasibility. No candidate is removed by Day 3. | Whole team |
| Data contract | Keep launch, landing, deployment and mission-end events distinct; retain coordinate type/frame, source links and uncertainty. Agree names and null handling before wiring the UI. | Data + frontend |

Researching model availability, sizes and usage terms remains Day 5 work. No model path or asset availability is promised here.

## Recovery provenance

[PR #1](https://github.com/nergisRahimzade/NASA-Space-Apps-Challenges-2026---Abandoned-but-not-Forgotten/pull/1) and [PR #2](https://github.com/nergisRahimzade/NASA-Space-Apps-Challenges-2026---Abandoned-but-not-Forgotten/pull/2) supplied Day 1/2 research; [PR #3](https://github.com/nergisRahimzade/NASA-Space-Apps-Challenges-2026---Abandoned-but-not-Forgotten/pull/3) merged the combined work into the former `master` branch. During the repository check, `master` is absent and current `main` points to `cfc9f6fcdcb309d4b9b7ea9707fd6a103a53c970`, which has only `data/.gitkeep`.

`candidates.md` is recovered from the existing Day 2 branch, with the same Git blob (`0859fdc826a122e0f6dc24c984c603909cf0b1a4`) recorded in [the PR #3 merge](https://github.com/nergisRahimzade/NASA-Space-Apps-Challenges-2026---Abandoned-but-not-Forgotten/tree/cfb96e9bc57f0558861233505f15d3b773112b18/data). This preserves prior work without merging the old branch history. The available history does not establish why the integration branch changed.
