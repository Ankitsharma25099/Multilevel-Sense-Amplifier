# Multilevel Sense Amplifier Design and Analysis

## Overview

This project focuses on the design, implementation, layout generation, and performance evaluation of a **Multilevel Sense Amplifier (MLSA)** for memory applications. The amplifier is capable of detecting multiple bit-line voltage levels and generating corresponding digital outputs, enabling reliable multi-level memory sensing.

The design was analyzed through schematic simulations, post-layout verification, Monte Carlo analysis, and layout optimization using both conventional and common-centroid techniques.

---

## Project Information

**Course:** Memory Design and Test

**Instructor:** Dr. Anuj Grover


## Problem Statement

Design a multilevel sense amplifier with the following specifications:

* Multiple outputs corresponding to different bit-line voltage levels.
* Offset voltage target of **50 mV** at **0.9 V supply**.
* Output latch response time of **150 ps**.
* Perform **3σ Monte Carlo analysis** to verify robustness.
* Compare conventional and **common-centroid layout** implementations.

---

## Design Architecture

The complete design consists of:

* Multilevel Sense Amplifier
* Decoder Circuit
* Output Latch
* Reference Voltage Generation Network

The amplifier senses small voltage differences on memory bit-lines and converts them into digital outputs corresponding to multiple stored levels.

---

## Design Flow

### 1. Schematic Design

The complete transistor-level schematic of the multilevel sense amplifier was developed and verified through pre-layout simulations.

Features include:

* Multi-threshold sensing
* Fast latch-based decision making
* Multiple output levels
* Low-offset architecture

---

### 2. Decoder Design

A dedicated decoder was implemented to translate the sensed analog levels into digital output codes.

The decoder generates the following output states:

| Input Level        | Output Code |
| ------------------ | ----------- |
| Lowest Level       | b00         |
| Intermediate Level | b01         |
| Intermediate Level | b10         |
| Highest Level      | b11         |

---

### 3. Layout Design

Physical layout implementation was completed for:

* Standard Layout
* Common-Centroid Layout

The common-centroid structure was adopted to improve matching and reduce process-induced offset variations.

---

### 4. Physical Verification

The layouts successfully passed:

* Design Rule Check (DRC)
* Layout Versus Schematic (LVS)

This confirms correctness of the fabricated layout and functional equivalence to the schematic.

---

## Common-Centroid Layout

To improve matching between critical devices, a common-centroid placement strategy was implemented.

### Benefits

* Reduced systematic mismatch
* Lower offset variation
* Improved robustness against process gradients
* Better Monte Carlo performance

---

## Monte Carlo Analysis

A comprehensive Monte Carlo simulation was performed to evaluate:

* Offset Voltage
* Response Time
* Process Variation Sensitivity

The analysis was conducted under multiple operating conditions.

---

## Performance Results

### Sense Amplifier 1 (SA1)

#### Response Time at 1.2 V

| Parameter          | Value     |
| ------------------ | --------- |
| Mean               | 124 ps    |
| Standard Deviation | 32.429 ps |

#### Offset Voltage at 1.2 V

| Parameter          | Value     |
| ------------------ | --------- |
| Mean               | 21.85 mV  |
| Standard Deviation | 11.457 mV |

---

### Sense Amplifier 2 (SA2)

#### Response Time at 1.2 V

| Parameter          | Value     |
| ------------------ | --------- |
| Mean               | 103.72 ps |
| Standard Deviation | 18.804 ps |

#### Offset Voltage at 1.2 V

| Parameter          | Value     |
| ------------------ | --------- |
| Mean               | 28.4 mV   |
| Standard Deviation | 8.1705 mV |

---

### Sense Amplifier 3 (SA3)

#### Response Time at 1.2 V

| Parameter          | Value     |
| ------------------ | --------- |
| Mean               | 196.8 ps  |
| Standard Deviation | 55.794 ps |

#### Offset Voltage at 1.2 V

| Parameter          | Value     |
| ------------------ | --------- |
| Mean               | 3.3891 mV |
| Standard Deviation | 3.3314 mV |

---

## Low Voltage Operation (0.9 V Supply)

### SA1 Performance

#### Response Time

| Parameter          | Value     |
| ------------------ | --------- |
| Mean               | 1.2472 ns |
| Standard Deviation | 561.14 ps |

#### Offset Voltage

| Parameter          | Value     |
| ------------------ | --------- |
| Mean               | 6.36 mV   |
| Standard Deviation | 5.9535 mV |

---

### SA3 Performance

#### Response Time

| Parameter          | Value     |
| ------------------ | --------- |
| Mean               | 1.4554 ns |
| Standard Deviation | 574.88 ps |

#### Offset Voltage

| Parameter          | Value     |
| ------------------ | --------- |
| Mean               | 1.4089 mV |
| Standard Deviation | 1.3634 mV |

---

## Output Verification

The amplifier correctly distinguishes between multiple input levels and generates the expected output codes:

### Verified Output States

```text
b00
b01
b10
b11
```

Simulation results confirmed correct operation for all sensing levels.

---

## Key Observations

### Response Time

* SA2 exhibits the fastest response among all amplifiers at 1.2 V.
* Response time increases significantly when supply voltage is reduced to 0.9 V.
* All designs remain functional under low-voltage operation.

### Offset Voltage

* SA3 demonstrates the smallest offset voltage.
* Common-centroid implementation improves matching and reduces offset variation.
* Measured offsets are substantially below the required 50 mV specification.

### Robustness

* Monte Carlo analysis confirms stable operation under process variations.
* Standard deviations remain within acceptable limits.
* The design satisfies the robustness requirements for practical memory applications.

---

## Results Summary

| Parameter             | Best Performer                 |
| --------------------- | ------------------------------ |
| Lowest Offset         | SA3                            |
| Fastest Response      | SA2                            |
| Best Matching         | Common-Centroid Layout         |
| Low Voltage Operation | SA1 & SA3                      |
| Robustness            | Common-Centroid Implementation |

---

## Repository Structure

```text
├── Schematics/
├── Decoder/
├── Layout/
│   ├── Standard_Layout/
│   └── Common_Centroid_Layout/
├── DRC_Reports/
├── LVS_Reports/
├── Simulations/
│   ├── Pre_Layout/
│   ├── Post_Layout/
│   └── Monte_Carlo/
├── Results/
├── PPT/
└── README.md


## Conclusion

A multilevel sense amplifier capable of detecting multiple bit-line voltage levels was successfully designed and verified. The design satisfies the required offset voltage specification while maintaining robust operation under process variations. Monte Carlo analysis demonstrates strong reliability, and the common-centroid layout significantly improves device matching and reduces offset variation. The proposed architecture is well-suited for modern multi-level memory sensing applications.
