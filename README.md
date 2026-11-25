# CMOS Differential Amplifier for Strain-Gauge Bridge Readout

A transistor-level design and simulation project exploring how a low-power CMOS amplifier can read the small voltage difference produced by a strain-gauge bridge.

**Authors:** Arnold Ackom ODURO and Hanz OFOSUHENE-SINTIM  
**Institution:** JUNIA ISEN  
**Original project:** November 2026

## The application

A strain gauge changes resistance when its supporting material stretches or compresses. A Wheatstone bridge converts that change into a small differential voltage, as used in load cells for weighing and force measurement.

Our demonstration uses four nominally 350-ohm resistors with 0.8 V excitation. Both bridge midpoints sit at 0.4 V when balanced. Changing one resistance by +/-0.1% produces approximately +/-200 microvolts between the midpoints. The amplifier makes this small difference easier to measure.

The application shaped the design priorities: differential gain, common-mode rejection around a 0.4 V input bias, low quiescent power, and adequate stability with a capacitive load.

## Circuit overview

The circuit follows an eight-transistor, two-stage architecture:

- A PMOS reference mirror supplies the bias currents.
- A PMOS differential pair and NMOS current-mirror load form the first gain stage.
- An NMOS common-source stage with a PMOS active load provides further gain.
- A Miller capacitor shapes the frequency response.

The circuit was designed and evaluated in Cadence Virtuoso with Spectre and the gpdk045 design kit. The amplifier supply is 1.1 V, and the specified output load is 1 pF.

## What this repository will document

The documentation will explain the device-sizing choices, standalone block tests, changes from the baseline circuit, complete-amplifier measurements, and the bridge demonstration. It will connect the saved simulation evidence to the reasoning behind each design choice.

The original circuit study is complete. We are organizing and publishing its documentation incrementally. This initial update introduces the application and architecture; diagrams, selected results, analysis, and the report will follow.

## Scope and dependencies

This is a nominal schematic-simulation study. Physical layout, fabrication, input-referred noise, random mismatch, and process-corner characterization remain outside the completed work.

Cadence software, gpdk045 models, technology-library files, and virtual-machine images are external dependencies and are excluded from this repository. Reproducing transistor-level simulations requires separately authorized access to the appropriate tools and design kit.
