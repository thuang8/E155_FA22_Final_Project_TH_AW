---
layout: page
title: Project Overview
permalink: /
exclude: true
---

<div style="text-align: left">
  <img src="./assets/img/hmc_logo.png" alt="logo" width="100" />
  <img src="./assets/img/Logo.png" alt="logo" width="100" />
</div>

# Project Abstract
Oscilloscopes and analog signal measurement tools are an essential part of electronics. At first glance, they simply record the magnitude of electronic signals, but hidden beneath is the ability to calculate important signal characteristics such as frequency content. These features were goals that the team set out to implement on a self fabricated oscilloscope created during the Fall 2022 semester. The oscilloscope designed by the team can be broken up into three main components that are outlined on this website. First, analog circuits are used to perform preprocessing on the raw input signal, such as filtering, and handle interactive functionalities including signal scaling and offsetting. This signal then enters the STM32 ADC where it is digitized and sent over SPI protocol to the FPGA. From there the FPGA displays the digitized data onto a 64 by 64 LED matrix. Each of these processes and the steps taken to accomplish these operations are outlined in individual sections on this website. The goal of this project was to become more technically versed with digital hardware, but the team came out of the project learning far more!


# Project Motivation

# System Block Diagram
