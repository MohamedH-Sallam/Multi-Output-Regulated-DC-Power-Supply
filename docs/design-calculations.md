# Design Calculations

Analytical formulations behind every stage of the supply, from transformer
selection through potentiometer dial position.

## 1. Transformer Headroom

A 12-0-12V center tapped step down transformer was selected to give the
regulators sufficient input headroom.

Peak secondary voltage:

```
Vpeak = Vrms × √2 = 12 × 1.414 = 16.97V
```

Accounting for the bridge rectifier diode drops (approximately 1.4V total):

```
Vpeak,rect ≈ 15.6V
```

Linear regulators typically need a 2 to 3V dropout margin, so this
transformer gives enough input headroom for stable regulation under load.

## 2. Rectification and PIV

A full wave bridge rectifier was used to maximize conversion efficiency and
raise the effective ripple frequency to 100Hz.

Required peak inverse voltage per diode:

```
PIV ≈ 17V
```

1N5408 diodes were selected for margin above this rating.

Average DC component of the rectified signal:

```
VDC = 0.637 × Vpeak = 0.637 × 15.6 ≈ 9.94V
```

## 3. Capacitive Filtering

RMS ripple content before filtering, derived from the RMS relationship:

```
Vrms² = Vr,rms² + VDC²
Vr,rms = √(Vrms² − VDC²)
```

With:

```
Vrms = Vpeak / √2 = 15.6 / 1.414 ≈ 11.02V
```

Substituting:

```
Vr,rms = √(11.02² − 9.94²) ≈ 4.76V
```

After adding the 2200µF filter capacitor, ripple is estimated by:

```
Vripple = VDC / (4 × √3 × f × C)
```

With f = 50Hz and C = 2200µF = 0.0022F:

```
Vripple = 9.94 / (4 × √3 × 50 × 0.0022) ≈ 0.48V
```

## 4. Linear Voltage Regulation

Fixed regulation stages:

- 7805 / 7905 for the ±5V rails
- 7809 / 7909 for the ±9V rails
- LM317 / LM337 for the adjustable ±12V rails

Adjustable output equation for the LM series parts:

```
Vout = 1.25 × (1 + R2 / R1)
```

## 5. Potentiometer Calibration

Target: Vout = 12V with a fixed base resistor R1 = 240Ω.

```
12 = 1.25 × (1 + R2 / 240)
12 / 1.25 = 1 + R2 / 240
9.6 = 1 + R2 / 240
R2 / 240 = 8.6
R2 = 2064Ω
```

Using a 5kΩ potentiometer, the corresponding dial position is:

```
Dial Position = 2064 / 5000 ≈ 0.41 → 41%
```

The 12V output is reached at roughly 40% rotation of the potentiometer
dial, which matched the behavior observed during calibration of the
physical unit.
