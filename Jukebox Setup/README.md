## Audio Devices
For simple setup, each audio device is asigned an id and variables are set accordingly.

- For a single track, only 2 devices are needed, and the notes will alternate between the two. In this case use ids 1 and 2.
- For a double track system, I recomend 6 devices so that track 1 is louder than track 2. For this use multiple copies of each id 1-2, and id 3-4 for the backing track.

For each device, rename the first field `SoundOn` to `P#` (ex. `P1`, `P2`), and the 5th field `SoundType` to N#. Set each `SoundCategory` to 3, and `Radius` to a large number, (such as 200). Leave everything else default (`TriggerRule`=-1, `RetriggerAmount`=1, everything else 0).

## System Chips
Your first 2-4 basic yolol chips are used to run the actual music, 2 for each track. Copy the respective file `Track#Chip#.yolol` into each and then just leave them alone. To add more tracks copy the track 2 chips again, replace `H` variables with a new letter and increment `N#` and `P#` variables by 2.

There should also be 1 memory chip, the list of values to include in that can be found in `SingleTrackMemoryChip.txt` or `DoubleTrackMemoryChip.txt`.

## Song Chips
Each song is given it's own id number, listed in the first line of the chip. These can be changed to anything based on personal ordering and your chosen song selection method.

They can all be placed in basic chips, though each one should also have `ChipWait` renamed to `SongLoad` and set to -1.

Every song file should follow this structure:
```
if :SongL==<id> then goto2 end goto1 // Song Name
...Build song into a and b variables...
:NowPlaying="Song : Artist : Transcriber"
:Trk1=a :Trk2=b goto1
```

Example songs are available in this repository, more info on creating songs there.

## Playing songs
A single `0` to `1` button is all that is needed to start and stop the music. Name it `Play`, with `ButtonStyle`=1.

Looping can be added by creating a second button named `Loop` with `ButtonStyle` 1, though the first chip for track 1 must be modified to support this feature. Instructions for that are included in `Track1Chip1.yolol`

## Song Selection
Selecting songs is simple and can be handled with multiple different methods. The only real thing that needs to happen is `SongL` gets set to the song id and `SongLoad` gets set to 0.

This can be done in many different ways, examples are in the Modules folder.

The `NowPlaying` text box should always be on it's own line in the song chip, so displaying it is optional.



