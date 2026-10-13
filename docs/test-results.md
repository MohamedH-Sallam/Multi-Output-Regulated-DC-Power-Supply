# Test Results

Empirical validation of the finished hardware against the NI Multisim
simulation, using a digital multimeter for DC levels and a Tektronix
DPO4104 digital phosphor oscilloscope for waveform integrity.

## Simulated vs Measured Output

| Rail Type | Simulated (V) | Measured (V) | Error |
|---|---|---|---|
| +5V Fixed | +5.01 | 4.93 | 1.59% |
| -5V Fixed | -5.03 | -4.96 | 1.39% |
| +9V Fixed | +9.01 | 9.29 | 3.11% |
| -9V Fixed | -9.01 | -9.08 | 0.78% |
| +12V Variable | +11.8 | 12.26 | 3.90% |
| -12V Variable | -11.9 | -12.27 | 3.11% |

Every rail landed within a 4% error band of its simulated target, which
confirms that component tolerances and soldering quality met the accuracy
required for the design.

## Oscilloscope Validation

Each output rail was probed directly at its terminal. The fixed ±5V and
±9V rails show a flat DC trace, which confirms that the 2200µF filter stage
and linear regulators remove the 100Hz rectified ripple. The adjustable
±12V rails show the same clean, flat behavior at their maximum dial
position.

### +5V Fixed Rail

![+5V fixed rail trace](../images/scope-plus5v.jpg)

### -5V Fixed Rail

![-5V fixed rail trace](../images/scope-minus5v.jpg)

### +9V Fixed Rail

![+9V fixed rail trace](../images/scope-plus9v.jpg)

### -9V Fixed Rail

![-9V fixed rail trace](../images/scope-minus9v.jpg)

### +12V Variable Rail (maximum)

![+12V variable rail trace](../images/scope-plus12v.jpg)

### -12V Variable Rail (maximum)

![-12V variable rail trace](../images/scope-minus12v.jpg)

## Interpretation

Negligible peak to peak noise across all six traces confirms that the
decoupling capacitors neutralize high frequency transients on every rail.
Combined with the DC accuracy table above, the finished supply is suitable
for powering and testing sensitive electronic instrumentation.
