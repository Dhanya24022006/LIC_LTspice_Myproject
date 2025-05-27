# 555 Timer IC Projects: Monostable & Astable Multivibrators

##  Aim

- To generate a pulse of width 0.5 ms using a 555 timer IC in **monostable** configuration.
- To implement an **astable multivibrator** circuit that triggers a **monostable multivibrator** through signal conditioning circuits.

## Theory

### Monostable Multivibrator

A **monostable multivibrator**, or one-shot multivibrator, has a single stable state. When it receives an external **trigger pulse**, it temporarily switches to an unstable state and then returns to the stable state after a time duration determined by the **RC time constant**.

- The pulse width (T) is given by:  
  `T = 1.1 × R × C`  
  where `R` is in ohms and `C` is in farads.
- After the capacitor voltage exceeds 2/3 of Vcc, the output returns to LOW.

### Astable Multivibrator

An **astable multivibrator** using the 555 timer produces a **continuous rectangular waveform** without any external trigger.

- The circuit oscillates between HIGH and LOW states.
- Time intervals are determined by two resistors and a capacitor.
  
  - `TON = 0.693 × (R1 + R2) × C`
  - `TOFF = 0.693 × R2 × C`
  - `T = TON + TOFF`

##  Working Principle

### Monostable Mode
1. When pin 2 voltage < 1/3 Vcc → Output goes HIGH.
2. Capacitor charges through resistor R.
3. When voltage at capacitor reaches 2/3 Vcc → Output goes LOW.

### Astable Mode
1. Capacitor charges and discharges alternately through resistors R1 and R2.
2. This switching creates a square wave output.


## Calculation (Monostable Mode)

Given:

- Desired pulse width: `T = 0.5 ms`
- Capacitance: `C = 0.1 µF`

Using formula `T = 1.1 × R × C`:


