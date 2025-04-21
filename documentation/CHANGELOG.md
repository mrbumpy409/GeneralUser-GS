# GeneralUser GS Revision History

## 2.0.2 (2025-04-21)

* Added exclusive class (self-muting) behavior to the following percussion kit sounds:
  - **Hi / Low Whistle**
  - **Guiro Short / Long**
  - **Cuica Mute / Open**
* Improved programming on **000:060 French Horns**. The lowest part of the instrument range is now a bit brighter, and I have better balanced the use of the filter across the entire key and velocity range. Partially addresses [issue #9](https://github.com/mrbumpy409/GeneralUser-GS/issues/9).
* Documentation updates:
  - Corrected reverb settings in SCUMMVM. Fixes [issue #13](https://github.com/mrbumpy409/GeneralUser-GS/issues/13).
  - Removed recommendations to use 7th-order interpolation in FluidSynth, as it can actually add distortions into the sound in some cases.
  - Removed outdated information.
* Support files updates:
  - Tweaked the Linux .desktop file for FluidSynth to match the case between filename and application name and to avoid launch feedback.

## 2.0.1 (2024-10-15)

* Removed the version number and space from the SoundFont filename so users can update the SoundFont without changing filename links that point to it.
* **000:007 Clavinet**: Improved note volume consistency across the key range. It is now better balanced with the Roland SC-55.
* Fixed **000:010 Music Box** volume envelope decay time; it was too short.
* **000:048 Fast Strings**: The volume envelope duration increase at lower velocities has been capped to avoid quiet notes starting too slowly.
* **000:049 Slow Strings**: The volume envelope duration decrease at higher velocities has been capped to avoid loud notes starting too quickly.
* Fixed clicking loops in the synth strings and synth bell samples used in **000:050 Synth Strings 1**, **000:088 Fantasia**, and many other pad presets.
* Re-programmed **000:098 Crystal** to more closely match the Roland Sound Canvas.
* Updated the license text embedded within the SoundFont to match `LICENSE.txt`.

## 2.0.0 (2024-9-19)

* Updated compatibility requirements (see `README.html` for more details).
* Reprogrammed all of the presets that use single-cycle analog waveforms using better waveforms that no longer create aliasing.
* Many changes were made to better emulate the behavior of the Roland Sound Canvas (SC-55 and SC-8820), including:
  - Re-balanced the volume of all instruments.
  - Increased reverb (CC91) and chorus (CC93) send amount.
  - Reverb level and reverb send amount is greatly reduced on drum kit kick drums.
  - Many instruments were adjusted or redesigned (see individual instrument notes below).
* Adjusted the filter balance and envelope of many instruments as well as other small tweaks here and there.
* Increased the velocity dynamic range of all harpsichords and organs. In previous versions of GeneralUser GS, harpsichords and organs had a greatly reduced dynamic range. This made them behave more like their real-world counterparts, but caused compatibility issues with MIDI files that use velocity to control an instrument’s volume. If you wish to experience these instruments without velocity affecting volume, you can find copies of the bank 0 instruments on bank 11 and copies of the bank 8 instruments on bank 12 with “noVel” in the preset name.
* Expanded key range up to MIDI note #108 (top note on an 88-key piano) for instruments that were previously restricted. Downsampled samples were created to make this extension work correctly on Audigy.
* Added new instrument **011:029 Wah Guitar (CC21)**. This preset is the Overdrive Guitar with a built-in wah pedal, controllable via MIDI CC #21.
* Added new drum kit **128:127 CM-64/32L** to complete support for all Roland SC-55 drum kits.
* **000:006 Harpsichord** and **008:006 Coupled Harpsichord**: Reprogrammed for more vibrant tone and varied note attack across the velocity range.
* **000:007 Clavinet**: Fixed buzzing loops, completely reprogrammed, and added simulated key release noise.
* **000:008 Celeste** and **000:010 Music Box**: Fixed buzzing loops, removed need for duplicate samples, added low velocity filtering. More consistent timing between voices in the music box.
* **000:011 Vibraphone**: More natural envelope and velocity response. I also added tremolo to the sound to better match Roland’s vision for the sound. I also added a version of the preset without the tremolo: **011:011 Vibraphone No Trem.**
* **000:019 Pipe Organ**: Transposed down an octave to match the tonality of the Sound Canvas.
* **008:021 Italian Accordion**: Fixed misspelling in preset name.
* **000:025 Steel Guitar** and **008:025 12-String Guitar**: Re-programmed for better velocity response and string decay sound.
* **016:025 Mandolin**: Re-programmed with new filter balance. This preset also now avoids the use of volume delay envelope, using an alternate method of creating a staggered string effect that provides much better results.
* **000:030 Distortion Guitar** and **008:030 Feedback Guitar**: Improved the programming and balance.
* **000:032 Acoustic Bass**: Better use of the filter.
* **000:033 Finger Bass**: Improved filter and mod envelope. Previous preset was too muffled in tone.
* **000:038 Synth Bass 1**: Better velocity response.
* **001:038 Synth Bass 101**: Reprogrammed to better match the Roland SC-8820.
* **008:038 Acid Bass**: Reprogrammed to better match the Roland SC-8820.
* **000:039 Synth Bass 2**: Re-programmed to better simulate FM bass velocity behavior.
* **000:044 Tremolo Strings**, **000:048 Fast Strings**, **000:049 Slow Strings**, and **011:049 Velo Strings**: Reprogrammed with quicker note response in the fast presets and a smoother note attack at lower velocities in all presets. Also slightly reduced the tremolo strength in the tremolo strings.
* **008:048 Orchestra Pad**: Brass layer has been raised an octave to match the Roland Sound Canvas.
* **000:060 French Horns** and **001:060 Solo French Horn**: Reprogrammed for better dynamic range and note attack. The valkyries should no longer sound like they’re riding through molasses.
* **000:062 Synth Brass 1**: Improved sound programming.
* **000:063 Synth Brass 2**: Reprogrammed to better match the Roland SC-8820.
* **000:071 Clarinet**: Better programming of the velocity response of both envelope and filter.
* **000:073 Flute**: Fixed bumpy loops and re-balanced the volume across the instrument’s range.
* **000:078 Whistle**: Re-programmed to match the Roland original. The previous version, called “Irish Tin Whistle”, has been split into emulations of the Roland SC-8820’s three tin whistle presets:
  - **024:075 Tin Whistle**: An Irish tin whistle that plays a short trill when velocity is 100 or greater.
  - **025:075 Tin Whistle Nm**: Same as above without the trill. This preset is identical to the old “Irish Tin Whistle” that used to be on **000:078**.
  - **026:075 Tin Whistle Or**: This version of the tin whistle preset always plays the short trill, regardless of velocity.
* **011:078 Whistlin'**: Replaced the AWE32 ROM white noise sample.
* **000:079 Ocarina**: The previous samples had many issues and have been replaced with old AKAI public domain samples.
* **001:080 Square Wave**: Reprogrammed to better match the Roland SC-8820.
* **000:081 Saw Lead**: Better volume and filter envelope behavior.
* **001:081 Saw Wave**: Reprogrammed to better match the Roland SC-8820.
* **008:081 Doctor Solo**: Completely reprogrammed using the new analog waveforms. I also removed the duplicate of this preset that was in bank 11.
* **012:081 Saw Lead 2**: Eliminated big jumps in velocity-to-filter scaling.
* **000:086 5th Saw Wave**: Envelopes now better match the Roland Sound Canvas.
* **000:087 Bass & Lead**: Completely reprogrammed using the new analog waveforms.
* **002:102 Echo Pan**: Reprogrammed to better match the Roland SC-8820.
* **008:118 808 Tom**: Fixed pitch and programming to match the toms in the 808 drum kit.
* **003:122 Wind**: Reprogrammed to better match the Roland Sound Canvas. The previous version of this preset, “Howling Winds” has been moved to bank 11.
* **000:123 Birds**: New sample and programming to better match the Roland Sound Canvas family behavior.
* **003:123 Bird 2**: Reprogrammed to better match the Roland SC-8820.
* **004:124 Scratch**: Corrected the preset number, which was 123 in previous versions.
* **012:127 Shooting Star**: reduced volume and added key number scaling of filter sweep effect
* **128:001 Standard Kit**: New primary snare with 3 sampled velocity layers. The old snare is now available in the **128:002 Standard 3** drum kit.
* **128:008 Room Kit**: Improved programming and sound of primary snare.
* **128:016 Power Kit**: New primary snare based on the new standard kit snare + gated effect layer.
* **128:025 808/909 Kit** and **128:026 Dance Kit**: Improved velocity response of second snare (TR-909).
* **128:032 Jazz Kit**: Improved velocity response of the snares.
* **128:048 Orchestral Kit**: Programmed a secondary kick that sounds more like a type of orchestral bass drum.
* **128:056 SFX Kit**: Updated with the new wind and birds sound effects.

Known Issues:

* The preset **008:014 Church Bells** will not sound correct in FluidSynth until version 2.4 (see [issue #1312](https://github.com/FluidSynth/fluidsynth/issues/1312)).

## 1.5.2 (2022-5-9 unreleased beta)

* **000:004 Tine Electric Piano**: Fixed buzzy loops and improved dynamics and tone.
* **000:041 Viola**: Improved note attack and tone across dynamic range. Fixed bad loops on samples 54, 77 and 82.
* Fixed Shaker and Cabasa samples in percussion presets being erroneously swapped.
* Further tweaks to the balance of the drums.
* Further improvements to primary and secondary snares in the standard drum kit.

## 1.5.1 (2020-11-20 unreleased beta)

* All acoustic pianos and harp: improved stretch tuning and overall instrument intonation.
* Improved sample programming on standard snares and brushed snares.
* Tweaked the intonation of many instruments.
* Reduced the entire SoundFont volume by 2 dB to satisfy negative attenuation values that didn’t have the dynamic headroom. The following instruments will still have a bit of attenuation when CC7 and velocity are at max:
  - **005:126 Footsteps**: 0.84 dB attenuation
  - **016:025 Mandolin**: 2.00 dB attenuation
* **000:011 Vibraphone**: improved loops for better pitch stability
* **000:041 Viola**: Restored original sample rate (variable, c. 30 KHz) instead of being downsampled to 22.05 KHz.
* **000:081 Saw Lead**: Improved with better attack and filter values, aiming to be more like the Saw Lead in the original Roland GM instruments.
* All **fast strings** presets: Improved note attack.
* All **acoustic guitar** presets: Improved decay envelope.
* Various fixes and tweaks.

## 1.5.0 (2020 unreleased beta)

* New version numbering scheme. I have adapted the semantic “Major.Minor.Patch” version scheme going forward.
* Major code cleanup, including :
  - Removed unnecessary modulators.
  - Moved duplicated data to the global zone.
  - Moved sample tuning info into the samples.
* Minor tweaks here and there.

## 1.472 (2019-8-20)

* Fixed a problem in all presets using the FM electric piano samples whereby notes would sound incorrect at velocity = 105.

## 1.471 (2017-2-7)

* Fixed missing chimes (C6) in Power and Orchestral drum kits.
* Fixed Marimba crashing MuseScore.

## 1.47 (2016-5-25)

* Unified the FluidSynth and MuseScore versions into a single version now that MuseScore bug #72091 (https://musescore.org/node/72091) has been fixed. This version has also been verified (and slightly tweaked) to work with the latest SynthFont2, which now supports SoundFont 2.01 modulators! Requires SynthFont2 2.0.3.2 or later, or VSTSynthFont 1.081 or later.

## 1.46 (2015-9-8)

* Fixed high-pitched squeal in Electric Grand
* Improved kicks and snares in Standard, Standard 2, Room, Power and Electronic drum kits
* Balanced C5 sample in the Bassoon to fit better with the adjacent samples
* Improved the Harpsichord and fixed weird loop buzz
* Improved the Tremolo Strings
* Slight tweak to attack on Accordion
* Improved clicking loops in Fretless Bass
* Fixed bad loops in all strings
* Fixed Recorder release (it was too short)
* Fixed weird attack and velocity→filter response in Chiffer Lead
* Fixed release in upper extreme range of Muted Trumpet
* Fixed flat loop in Acoustic Bass

## 1.45 (2012-3-20)

* Tweaked velocity scaling in FluidSynth version to be less extreme between FF and PP playing.
* Fixed Slap Bass 1 and 2 release to avoid clicks in FluidSynth.

## 1.44 (2012-1-27)

* New license
* Fixed loops in Concert Choir
* Improved Bagpipes
* FluidSynth/MuseScore version: improved programming of harpsichord, trumpet, trombone, muted trumpet, and pan flute.
* MuseScore version: adjusted balance of orchestral instruments
* MuseScore version: modified default drum kit with orchestral bass drum, snare and cymbals.

## 1.43 (2009-2-6)

* Various improvements
* Re-worked strings in Live/Audigy version
* Separate versions for Live/Audigy, FluidSynth and other software synths
* Removed brand and product name references from presets

## 1.4 (2005-11-20)

* Countless samples have been replaced, improved, cleaned, re-looped, etc.
* Just as many instruments have been reworked, rebalanced, etc.
* Improved overall instrument volume and balance
* Previous versions of GeneralUser GS only allowed 20% of the total reverb and chorus effects to be used (this is the default setting in the SoundFont specification).  Setting reverb (CC91) or chorus (CC93) to max value (127) now allows 100% of the effect to be heard.
* Added self-test mode (activated by playing `GUTest.mid`)
* There are too many improvements in this bank to list, you will have to hear it for yourself :)

## 1.35 (2004-6-26)

* Made compatible with Sound Blaster Audigy and EMU APS.
* Minor tweaks.

## 1.3 (2001-4-30)

* Combined AWE32/64 and Live! versions into one bank compatible with both sound cards.
* Resampled Marimba.
* Standard snare now sounds much more realistic.
* Cymbals act appropriately when played soft, making decent-sounding cymbal rolls possible.
* Replaced Synth Brass 1, Square Lead and Sawtooth lead.  The old Square Lead and Sawtooth lead can be found in bank 12.
* Countless other modifications to instruments in the bank, including balance fixes.

## 1.2 (2000-10-30)

Both versions:
* Adjusted piano 1 and 2 brightness.
* Adjusted tuning of Marimba — attack still sounds strange in Live! version, can’t figure out why.
* Fixed crackling in Clean Guitar (and variants).
* Increased volume of high Trumpet notes.
* Other small changes.

Live! version:
* Fixed Hi-hat cutoff bug that showed up courtesy of the Creative Labs driver.
* Fixed bad attack on Harpsichord sound.
* Fixed some more synth sounds that weren’t right because the Live! driver screwed up the filter settings.

## 1.1 (1997-9-11)

Both versions:
* Reworked the string ensemble using same samples.  Sounds more full now and is in stereo.
* Adjusted balance/envelopes of some woodwinds.
* Made orchestral snare velocity sensitive.
* Other small tweaks here and there.

Live! version:
* Fixed some synth sounds that weren’t right because the Live! driver screwed up the filter settings.

## 1.0 (1997-5-29)

First release.
