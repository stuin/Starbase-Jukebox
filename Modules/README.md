# Optional Modules

## Song Selection

### Menu Lever
Based on a gearshift I designed for another project, this lists out the names of up to 6 songs on a text display and allows a normal sliding lever to be used to swap between them.

1. Copy `SelectMenuLever.yolol` into a basic chip.
2. Create a lever with value `SongL`, min 1, max 6, and center 1.
3. Add a text display next to it with value `Song`.

Also note with many of these methods, if you are creating new songs and live editing the code in game, you can create a `SongLoad` button with `OffState` -1 and `ButtonStyle` 1 to refresh the currently selected song.

### Next Button
For more compact, cd player style controls, simple `Play` and `Next` buttons can be placed alongside a `NowPlaying` text panel or progress bar. Optonally `Next` can be replaced with a switch to go both ways, or a `Prev` button can be included. 

To use this system copy `SelectNextButton.yolol` into a basic chip and place controls to your preferences. With this it is very important to fill every song index from 1 to maxL, as defined in the chip. Also remember to store `SongL` somewhere.

## Vizualizer (WIP)

Currently set up for a sideways basic grid display, `Visualizer1.yolol` displays Track1 as a waveform quite reliably.
Adding `Visualizer2.yolol` results in some bugs with the wave stalling but adds Track2 below Track1. `CursorX=CX` and `Input=SV`