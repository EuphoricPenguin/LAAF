<div align="center">
	<h1>
	<img src="./LAAF Logo.png" width=100px alt="LAAF Logo"><br>LAAF
	</h1>
	<p>LMMS AI-Assisted Fork</p>
</div>

## What is LAAF?

LMMS AI-Assisted Fork (LAAF) is an open-source fork of [LMMS](https://github.com/LMMS) with the philosophy of creating experimental changes and building primairly for x64 Windows.

The goal of LAAF is to implement changes that I feel improve the user experience, take risks with redefining the included software, and generally reshape the program into something new and interesting. LMMS as a DAW is mature and very usable in its own right, but small annoyances have made me curious how far I could get at maintaining a fork.

## What does AI-Assisted mean?

Changes directly made to the codebase will be initiated with and mostly undertaken by Void Agent/DeepSeek. Given the nature of the changes, which may be breaking with LMMS, the general unpredictability of changes made using AI, and the fact that this fork aims to mirror the pre-release codebase, this fork is very much experimental and should not be considered stable. This fork is entirely about exploring limits in making complex changes to a large preexisting codebase, which is something I have never done before. This isn't about grasping for accolades; I just want to make my favorite program think a bit more like I do.

## Proposed Changes:
- [x] Importing a sample (if it's fairly long/more than a few bars) crops the sample
- [ ] The mixer panel no longer allows for the labels to be expanded
- [ ] No swing option for tempo in the pattern editor
- [ ] No option to change file paths of samples in save files
- [ ] Default theme is not frutiger aero
- [ ] The pack-in delay effect is hard to use and fiddly for fine-tuned effects
- [ ] Add Vitalium to default instruments
- [ ] Add ChowDSP effects
- [ ] No VST3 support/Add Element code directly to LMMS (similar to CARLA) for VST3 native support
- [ ] No obvious way to add MIDI input to effects from a piano roll track
- [ ] Get LPC.LV2 working on Windows and add it as an effect https://github.com/lewark/lpc.lv2
- [ ] Add Dexed with DX7 patch generator as pack-in instrument
- [ ] Create some sort of AI or vocaloid-type program as a default instrument
- [ ] Integrated Demucs support from UVR

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