---
layout: page
title: Analog Circuit Design
permalink: /analogdesign/
---


# Analog Circuit Design
<div style="text-align: center">
  <img src="../assets/schematics/analog.png" alt="fpgaoverview" width="800" />
</div>

The goals of the analog front-end are to provide an antialiasing filter, signal amplification, signal attenuation, signal offset, and time scaling. The analog front end contains a main circuit, and a probe. The probe is a hand-made shielded cable that elminates magnetic disturbances on the input signal wire.

The analog circuit contains 5 main stages: the Sallen-Key low-pass filter, the amplifier, the attenuator, the offsetter, and the unity gain buffer.


## Sallen-Key filter
The Sallen-Key filter with a corner frequency of 100khz. Ideally, this stage should prevent signal aliasing. 
However, the last-minute inclusion of time divisions means that the filter is insufficient for lower sampling rates. Because the corner frequency is fixed, noise below 100khz but above the sampling rate can still cause aliasing.

## Amplifier
The amplifier stage is modeled after a guitar amplifier circuit from an E84 homework assignment. This amplifier circuit is non-inverting to prevent negative feedback instability from a 180 degree phase shift.

## Attenuator
The attenuator stage is a variable voltage divider connected to an op amp in unity gain negative feedback. The purpose of the op amp is to prevent loading between circuit stages.

## Offsetter
The offsetter stage contains a variable voltage divider. The output from this divider is added to the input signal to create the offset. The large capacitor near the input of the circuit prevents the output of this stage from attenuating near 1-10 hz.

## Unity Gain Buffer
The purpose of the unity gain buffer is to limit the voltage range of the signal to make it safe for the ADC. The ADC can take input voltages from 0 to 3.3 volts reliably, and may break if the input signal is above 4 volts. 

Because the Op Amp is configured in a unity gain negative feedback loop, the manufacturer characterstics can have a large impact on signal quality.

Op Amp rail hysteresis was a problem the team encountered when adding the unity gain buffer to the rest of the circuit. Rail hysteresis caused the signal to "jump" to the rail, even if the signal value was below the rail. Eventually, this distortion was lessened when the analog circuit was moved from the breadboard to the perfboard. 

## The Probe
Initially, the probe was designed according to traditional oscilloscope probe schematics. During testing, the probe behaved like a low pass filter, and attenuated desired signals. Due to time limitations, the decision was made to elminitate the probe circuitry, and convert the probe into a shielded cable. 