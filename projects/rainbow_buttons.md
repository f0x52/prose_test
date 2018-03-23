---
layout: default
title: rainbow buttons
permalink: /projects/rainbow_buttons/
nolink: true
---
I've recently started upgrading old elevators, with LED's, which makes them look great. I started
with a rectangular one, for our hackerspace's nomzknop. After that the challenge continued with the
round version.
<div class="gallery">
    <img src="/media/rainbow_buttons/rect_finished.png" alt="Rectangular RGBW Button">
    <img src="/media/rainbow_buttons/round_finished.png" alt="Round RGBW Button">
</div>

These are the original internal pcb's of both:
<div class="gallery">
    <img src="/media/rainbow_buttons/rect_original.png" alt="Original Rectangular PCB">
    <img src="/media/rainbow_buttons/round_original.png" alt="Original Round PCB">
</div>
I've done quite a few iterations of the rectangular pcb, breaking some of the LED's or having other trouble.
<div class="gallery">
    <img src="/media/rainbow_buttons/rect_pcb1.jpg" alt="Rectangular PCB">
    <img src="/media/rainbow_buttons/rect_pcb2.jpg" alt="Rectangular PCB">
</div>
It has 4 SK6812 RGBW LED's, in comparison to the default 4 orange ones. A 2x2 header on the back exposes 5v, ground, data pin and the button lead, which connects to ground when pressed.
This is the finished frontpanel, a huge improvement in my opinion:
<img id="img" src="/media/rainbow_buttons/rect_finished.png" alt="Finished Rectangular frontpanel">

After this, it was time for the round one.  
This proved a bit more of a challenge, because of the limited pcb space, and being round.
My first finished round button went into the <a href="/projects/mario_box">mario box</a>, and I only made pictures of the back and front, when it was already assembled. For our hackerspace's light switches, I decided to document the process a lot better.
First got 2 square protoboards, by cutting with a boxcutter, and then breaking
<img id="img" src="/media/rainbow_buttons/round_pcb1.png">
Then I made them round using the same method, and drilled 2 holes to fit the button's plastic extruders.
<img id="img" src="/media/rainbow_buttons/round_pcb2.png">
After that I fit the 4 SK6812 LED's, and soldered them in place
<img id="img" src="/media/rainbow_buttons/round_pcb3.png">
The button goes in the middle, and had to have the stem fit well, cutting a bit, and then adding some hotglue
<img id="img" src="/media/rainbow_buttons/round_pcb4.png">
Then I laid out the wires to connect everything. Because it fits better, the LED's are connected a bit unintuitively, like this:
    2  1
    3  4
Which has to be corrected in software.
<div class="gallery">
    <img src="/media/rainbow_buttons/round_pcb5.png">
    <img src="/media/rainbow_buttons/round_pcb6.png">
</div>
Which gives the finished buttons:
<img id="img" src="/media/rainbow_buttons/round_finished.png">


