# Saw Animator

```
     |\
<--> | \ | <-->
        \|
```

The Saw Animator combines a signal from an LFO with a saw audio signal to produce interesting overtones. In effect the LFO modulates the frequency of the saw wave causing the waveform to dance side-to-side on the oscilloscope. This module has an LFO of its own with adjustable rate, this can be overridden with a different CV signal.

The circuit here is based on the [Yusynth Saw Animator](https://yusynth.net/Modular/EN/SAWANIM/index.html) with minor tweaks to make it more Eurorack friendly. The changes I've made are thus:
* Selected resistors appropriate for +/-12V rails,
* Added polarity protection so that a backward power header doesn't fry anything (twin series schotty diodes: BAT54SL),
* Full surface mount design.

The Yusynth page is a treasure trove of information about this circuit that I am too amateur to claim as my own; please read that outstanding page before using this circuit. The page provides many details and other implementations of this circuit that you may find suitable.

The KiCAD project here uses the library/footprints [found in my companion repo](https://github.com/thismatters/EurorackKiCAD).

## Width

10hp on an Intellijel 1U rack.

## Inputs

Single potentiometer for adjusting LFO rate. Input jack for control voltage which overrides the LFO. Input jack for saw audio signal.

## Outputs

Output jack for animated saw output. LED which tracks the internal LFO.

## Adjustment

### Refine shape

- Ground the LFO input
- Connect a balanced saw wave (+/-5V) to the input
- Connect oscilloscope to the output
- Adjust RV2 (the one in the middle layer) until the triangle looks smooth

###  Set Balance

- Adjust RV1 so that the output is blanaced in the +/-5V range.

## Vendors

There are part numbers in the [BOM](saw-animator.csv) for many of the parts (not for basic passives though) at the following vendors:

* [Mouser](https://www.mouser.com): Needs no introduction. Get your ICs from here (or [digikey](https://www.digikey.com)).
* [Tayda Electronics](https://www.taydaelectronics.com/): Good supplier for passive components; audio jacks, and potentiometers. Their audio jacks are slightly smaller than the thonkiconn from thonk.
* [Love My Switches](https://lovemyswitches.com/): Has [really good knobs](https://lovemyswitches.com/anodized-aluminum-knob-the-lo-fi-1-4-smooth-shaft-12-5mm-od/) to go on those potentiometers!
* [OSHPark](https://oshpark.com/): Fast and (relatively) cheap PCB manufacturer. [V0 PCB](https://oshpark.com/shared_projects/MXBVaxpS)


## Issues

### V0
- The output saw waveshape is slightly distorted at the bottom, the slope is a little off
- Assembly was harder than necessary because the two boards with SMD components did not have enough support tabs to keep them together; each board had to be registered for solder paste application separately.
