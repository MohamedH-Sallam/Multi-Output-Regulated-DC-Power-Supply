# Multi-Output Regulated DC Power Supply

**Project status: Published** · Electrical Engineering II (MNG 232) · Nile University · May 9, 2026

A six-rail linear regulated DC power supply delivering fixed ±5 V and ±9 V outputs alongside adjustable ±12 V outputs. The project progressed from NI Multisim simulation and analytical design calculations to a soldered hardware prototype and empirical validation.

> **Project website:** [Open the visual project showcase](https://mohamedh-sallam.github.io/Multi-Output-Regulated-DC-Power-Supply/)  
> **Repository:** [Source files on GitHub](https://github.com/MohamedH-Sallam/Multi-Output-Regulated-DC-Power-Supply)

| | |
|---|---|
| Design team | Abdullah Salem, Abdullah Mohamed, Mohamed Sallam, Ziad Ali |
| Supervisor | Dr. Mohamed Elhossainy |
| Course | Electrical Engineering II (MNG 232) |

## At a glance

- **Six regulated rails:** +5 V, −5 V, +9 V, −9 V, adjustable +12 V, adjustable −12 V.
- **Power architecture:** 12-0-12 V center-tapped transformer, 2W005G full-wave bridge rectifier, 2200 µF filtering, linear regulation, and output decoupling.
- **Regulators:** 7805, 7905, 7809, 7909, LM317, and LM337.
- **Validation:** NI Multisim, analytical calculations, digital multimeter, and Tektronix DPO4104 oscilloscope.

## Measured results

| Rail | Simulated | Measured | Error |
|---|---:|---:|---:|
| +5 V fixed | 5.01 V | 4.93 V | 1.59% |
| −5 V fixed | −5.03 V | −4.96 V | 1.39% |
| +9 V fixed | 9.01 V | 9.29 V | 3.11% |
| −9 V fixed | −9.01 V | −9.08 V | 0.78% |
| +12 V adjustable | 11.8 V | 12.26 V | 3.90% |
| −12 V adjustable | −11.9 V | −12.27 V | 3.11% |

All reported rails measured within 4% of their simulated targets. See [full test results and oscilloscope evidence](docs/test-results.md).

## Hardware prototype

![Assembled six-rail regulated power supply](images/assembled-prototype.jpg)

The prototype uses a soldered board and custom enclosure with front-panel output terminals, a ground reference, adjustment dials for the variable rails, and power-indicator LEDs.

## Signal path

1. 12-0-12 V center-tapped step-down transformer
2. Full-wave bridge rectifier (2W005G)
3. Capacitive filtering (2200 µF per rail, as documented)
4. Fixed and adjustable linear regulators
5. Output decoupling (100 nF and 10 µF)
6. Output terminal block and LED rail indicators

## Documentation

- [Design calculations](docs/design-calculations.md) — transformer, rectifier, filter, and regulator calculations
- [Bill of materials](docs/bill-of-materials.md) — components used in the design
- [Test results](docs/test-results.md) — simulated-versus-measured comparison and oscilloscope traces
- [Visual project page](docs/index.html) — responsive overview and prototype gallery

## Team

Abdullah Salem · Abdullah Mohamed · Mohamed Sallam · Ziad Ali

**Supervisor:** Dr. Mohamed Elhossainy

## Safety

**Mains-voltage warning:** This project interfaces with 220 V AC mains. Assembly, inspection, and operation must be performed only by people trained in electrical safety, with appropriate isolation, enclosure, fusing, and supervision. This documentation is not a safety certification.

---

*Project status: Published. Technical claims and measured values reflect the project records; they should not be interpreted as certification of load regulation, thermal performance, or electrical safety.*
