# IEC 62443 for Building Systems: ISO 27001 and UAE IA Crosswalk

A requirement-by-requirement map of **ISA/IEC 62443** to **ISO/IEC 27001:2022** and the **UAE Information Assurance (IA) Regulation**, written for the operational technology inside buildings: BMS, HVAC controls, lighting, AV, CCTV, access control and lift gateways.

**Headline:** an ISO 27001 ISMS fully covers 15 of the 31 requirements mapped here. 14 are partly covered and 2 have no ISO equivalent. Most of the shortfall is not missing controls. It is scope and method: building systems are left outside the ISMS, risk is scored on data rather than safety, and nobody owns the integrator's remote access.

| ISO 27001 coverage | Requirements |
| --- | --- |
| Covered | 15 |
| Partial | 14 |
| Gap | 2 |

## Who this is for

- ISMS owners whose certificate scope stops at the corporate network while the building runs on its own.
- Facilities and property managers who hold the BMS and AV contracts but not the security risk.
- Integrators and maintainers asked to show they meet IEC 62443-2-4 as a service provider.
- Auditors planning a review that includes building or operational technology.

## What is in the repo

| File | What it holds |
| --- | --- |
| [`crosswalk.csv`](crosswalk.csv) | 31 rows. Columns: ID, IEC 62443 reference, foundational requirement, requirement (paraphrased), building example, ISO 27001:2022 clauses and Annex A controls, UAE IA control family, ISO coverage rating, gap note, and the evidence an auditor would ask for |
| `CHANGELOG.md` | Version history |
| `LICENSE.md` | CC BY 4.0 |

Open the CSV in Excel or Google Sheets and filter on `iso_coverage` to see Partial and Gap rows first.

## Where an ISO 27001 ISMS falls short

| ID | IEC 62443 | Rating | Why ISO 27001 does not fully cover it |
| --- | --- | --- | --- |
| OT-05 | 3-2 | Gap | Target security level per zone has no ISO equivalent |
| OT-30 | 3-3 | Gap | Security controls must not block safety and life-safety functions |
| OT-01 | 2-1 | Partial | Building systems are usually outside the ISMS scope |
| OT-03 | 3-2 | Partial | Risk must include safety and physical consequences, per zone |
| OT-04 | 3-2 | Partial | Segregation exists in ISO; a documented zone and conduit model does not |
| OT-06 | 2-4 | Partial | Integrators must show defined security capabilities, not just sign clauses |
| OT-07 | 2-3 | Partial | OT patching needs vendor qualification and documented exceptions |
| OT-09 | SR 1.2 | Partial | Legacy building protocols cannot authenticate devices |
| OT-13 | SR 1.13 | Partial | Every remote and cloud path into the building must be known and monitored |
| OT-18 | SR 3.1 | Partial | Unencrypted BACnet and Modbus need compensating controls |
| OT-20 | SR 3.3 | Partial | Security tests belong in factory and site acceptance |
| OT-21 | SR 3.4 | Partial | Firmware integrity checking, beyond change control |
| OT-25 | SR 6.1, 6.2 | Partial | Monitoring that covers IT only does not see the control network |
| OT-26 | SR 7.1 | Partial | Essential functions must keep running in a degraded state |
| OT-27 | SR 7.3, 7.4 | Partial | The client often holds no copy of its own control code |
| OT-31 | 4-1, 4-2 | Partial | Procurement should ask for secure products and secure vendors |

## Method

1. Took the IEC 62443 requirements that apply to an asset owner running building systems: the programme (2-1), patching (2-3), service providers (2-4), risk assessment and zones (3-2), the system requirements in 3-3 that matter most on a building site, and product procurement (4-1, 4-2).
2. Paraphrased each requirement. The IEC 62443 documents are copyright and paywalled (62443-1-1 aside), so this repo does not reproduce them. System requirements are cited by SR number only.
3. Added a building example for each row, drawn from the kind of finding seen on site walks.
4. Mapped each requirement to ISO/IEC 27001:2022 clauses and Annex A controls, and to UAE IA control families (M1 to M6, T1 to T9).
5. Rated ISO coverage: **Covered** means a well-run ISMS with building systems in scope meets it; **Partial** means the ISMS meets part of it; **Gap** means ISO has no equivalent.
6. Added the evidence an auditor would reasonably ask to see.

## Limits

- The mapping and ratings are the author's professional judgement, not IEC, ISA or TDRA guidance. Two practitioners could rate some rows differently.
- This is a selection, not the full 3-3 catalogue. Requirement enhancements and security-level detail are left out.
- UAE IA is mapped at control family level, not individual control.
- Ratings assume building systems are in the ISMS scope. If they are not, most Covered rows become Gaps in practice (see OT-01).
- This is not legal advice and not a substitute for the standards themselves.

## Sources

- ISA: [ISA/IEC 62443 series of standards](https://www.isa.org/standards-and-publications/isa-standards/isa-iec-62443-series-of-standards)
- IEC Webstore: [62443 parts](https://webstore.iec.ch/searchform&q=62443) (62443-1-1 is free to read)
- Open Security Architecture: [IEC 62443-3-3 overview](https://opensecurityarchitecture.org/frameworks/iec-62443) and TeepTrak: [IEC 62443-3-3 system requirements](https://teeptrak.com/en/iec-62443-3-3-system-requirements-2026/), used to check SR numbering
- ISO/IEC 27001:2022 and Amendment 1:2024
- UAE Information Assurance Regulation (TDRA, formerly the NESA standard)

## Related

- [cbuae-orm-cyber-crosswalk](https://github.com/CyberHak44/cbuae-orm-cyber-crosswalk): the same method applied to the CBUAE Operational Risk Management Regulation.

## Contributing

Rate a row differently, or have a building example that fits better? Open an issue with the row ID (for example `OT-13`) and your reasoning.

## Author

**Clive (Hakim) Bean**: ISO/IEC 27001 Lead Auditor (GRC Mastery, 2026, Credly-verified). UAE and GCC cyber governance, risk and compliance, with 20 years in IT, network and OT infrastructure. Abu Dhabi.

Licensed under [CC BY 4.0](LICENSE.md).
