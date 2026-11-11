---
title: "Drum Robot Exoskeleton V1"
summary: "A wrist exoskeleton that teaches you to play drums"
thumbnail: /assets/images/projects/desk-lamp.svg
order: 1
---

<!-- ![Articulated desk lamp](/assets/images/projects/desk-lamp.svg) -->
# Overview
This is a powered-exoskeleton for the wrists that teaches you to play drums, and create muscle memory so that even after taking off the exoskeleton, you can still play the pattern. It uses a python script to parse the drum tracks from a MIDI file, and sends the relevant timing & track information to an MCU, which controls the wrist joint motors of the exoskeleton and moves the user's hands in the right timing.

## How it started
I played the drums in a band with my friends, but I've never played before. I watched a bunch of YouTube videos on drums, and stumbled upon a Jacob Collier polyrhythm video. I tried to tap out a 2-3 polyrhythm, which was manageable; then I tried a 3-4 polyrhythm, and failed miserably. 

I thought about how young children can learn things (like using a spoon) when their parents hold their hands to teach them. Maybe it's also possible to learn drums if someone (or some robot) is holding my hands? That's how the idea was formed: make a powered exoskeleton that controls the wrist joints, and moves my hands in the right timing of a polyrhythm (or any drum beat).


# Hardware Design
The V1 design is quite simple, as it's meant to be a proof-of-concept to see whether a robot can actually teach me the muscle memory of drum patterns and two-hand coordination. Spoiler: it can!

The system consists of two independent exoskeletons for the left and right hand, each driven by a MG996 servomotor. A quick-detach clamp mechanism fixes the exoskeleton to the wrist. The clamps are printed from TPU to conform to the shape of the wrist. A low profile thin-wall bearing is placed at the virtual rotation axis of the wrist (Ulnar deviation), and a drumstick is attached to the rotating piece for the user to hold onto. The servo moves the drumstick via a 4-bar linkage, which in turn moves the hand.

The two servos are controlled by a RP2040 microcontroller, and the whole system is powered by a 2s LiPo battery. The MCU can store pre-programmed drum patterns, or it can be connected to a computer running a python script that parses the drum tracks from a MIDI file. 
