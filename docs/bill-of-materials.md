# Bill of Materials

Full component inventory used in the final physical assembly.

| Component | Part Number / Value | Quantity |
|---|---|---|
| Transformer | TRAN-2P3S | 1 |
| Bridge Rectifier | 2W005G | 1 |
| Filter Capacitors | 2200µF / 25V | 2 |
| Decoupling Capacitors | 100nF / 0.1µF | 6 |
| Output Capacitors | 10µF | 4 |
| Fixed Regulators | 7805, 7905, 7809, 7909 | 4 |
| Variable Regulators | LM317, LM337 | 2 |
| Protection Diodes | 1N4001 | 8 |
| Potentiometers | 5kΩ | 2 |
| Resistors | 240Ω, 500Ω, 560Ω | 8 |
| LED Indicators | Red / Green | 6 |

## Notes

- Protection diodes (1N4001) guard the regulators against reverse current
  and reverse polarity conditions at the output terminals.
- Decoupling capacitors (100nF) sit close to each regulator's input and
  output pins to suppress high frequency transients.
- Output capacitors (10µF) are placed at each regulated rail to improve
  transient response under load changes.
- The two 5kΩ potentiometers set the adjustable ±12V rails via the LM317
  and LM337 feedback network described in
  [design-calculations.md](design-calculations.md).
