<div align="center">
	<h1>
	<img src="./LAAF Logo.png" width=100px alt="LAAF Logo"><br>LAAF
	</h1>
	<p>LMMS AI-Assisted Fork</p>
</div>

## What is LAAF?

LAAF is an open-source fork of [LMMS](https://github.com/LMMS) with the philosophy of creating experimental changes and building for x64 Windows.
The goal of LAAF is to implement changes that I feel improve the user experience, take risks with redefining the included software, and generally
reshape the program into something new and interesting. LMMS as a DAW is mature and very usable in its own right, but small annoyances have made me
curious how far I could get at maintaining a fork. LAAF isn't supposed to be a flex; I just want to customize my favorite FOSS program.

## Here are some of the things I'm aiming to slowly implement/fix:
1. Importing a sample (if it's fairly long/more than a few bars) crops the sample
2. The mixer panel no longer allows for the labels to be expanded
4. No swing option for tempo in the pattern editor
5. No option to change file paths of samples in save files
6. Default theme is not frutiger aero
7. The pack-in delay effect is hard to use and fiddly for fine-tuned effects
8. Add Vitalium to default instruments
9. Add ChowDSP effects
10. No VST3 support/Add Element code directly to LMMS (similar to CARLA) for VST3 native support
11. No obvious way to add MIDI input to effects from a piano roll track
12. Get LPC.LV2 working on Windows and add it as an effect https://github.com/lewark/lpc.lv2
13. Add Dexed with DX7 patch generator as pack-in instrument
14. Create some sort of AI or vocaloid-type program as a default instrument
15. Integrated Demucs support from UVR

## Features

* Song-Editor for arranging melodies, samples, patterns, and automation
* Pattern-Editor for creating beats and patterns
* An easy-to-use Piano-Roll for editing patterns and melodies
* A Mixer with unlimited mixer channels and arbitrary number of effects
* Many powerful instrument and effect-plugins out of the box
* Full user-defined track-based automation and computer-controlled automation sources
* Compatible with many standards such as SoundFont2, VST(i), LADSPA, GUS Patches, and full MIDI support
* MIDI file importing and exporting

## Building

See [Compiling LMMS using MSYS2](https://github.com/LMMS/lmms/wiki/dependencies-windows#windows-msys2)