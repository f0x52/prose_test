---
layout: default
title: ledspace
permalink: /projects/ledspace/
nolink: true
---

To color up my local hackerspace, I proposed to make 13 RGB tube lights. After getting a budget and waiting for Aliexpress, the fun could begin.  

As a base I'm using Hornbach's <a href="https://www.hornbach.nl/shop/LED-Armatuur-20-Watt-1200-mm-koel-wit-Energieklasse-A/5825358/artikel.html"> White LED Tube Light</a>, which offer a beautiful diffuser with aluminium heatsink.  
We start by tearing it down, which is surprisingly easy:
<img id="img" src="/media/ledspace/teardown.png">
After  removing the white led pcb, it's time to glue 1.2 meters of APA102 strip in it's place.
<img id="img" src="/media/ledspace/strip.png">
For c onnecting the tubes, I'm using RJ45 connectors. the TX pair (orange) for data, and the Power pair (brown) for clock. They are both twisted with a ground.
<img id="img" src="/media/ledspace/strip solder update.png">
The R J45 connector fits snuggly inside the casing
<img id="img" src="/media/ledspace/wires.png">
The P SU consists of 2 USB plugs, and an IKEA KOPLA power supply
<img id="img" src="/media/ledspace/psu.png">
On th e other side of the tube is another RJ45, which transfers ground, clock and data to the next tube
With  two connected togeather, it already looks great!
<img id="img" src="/media/ledspace/final.png">
Here  I installed the first two, driven by an Arduino Nano. Later on, a Raspberry Pi Zero W will take it's place.
<img id="img" src="/media/ledspace/final2.png">





