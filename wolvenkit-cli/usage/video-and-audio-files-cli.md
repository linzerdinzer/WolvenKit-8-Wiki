---
description: Extracting and playing from archives
---

# Video and audio files (CLI)

## Archives

Required files are contained within these archives

* audio\_1\_general.archive
* audio\_2\_soundbanks.archive
* basegame\_5\_video.archive
* lang\_en\_voice.archive

## Video files

Using [Wolvenkit Console](https://github.com/WolvenKit/WolvenKit-nightly-releases/releases/latest), decompress **basegame\_5\_video.archive** located at: `<gamedir>\Cyberpunk 2077\archive\pc\content`.

Do this by using the command prompt on your PC (Windows key+R, then enter **cmd** in the Run window), using the **cd** command to point the command prompt to the directory where you keep WolvenKit.Cli.exe, and using the following to command WolvenKit.Cli.exe to unbundle the desired archive into the desired depot folder.

```
WolvenKit.Cli.exe unbundle -p "<gamedir>\Cyberpunk 2077\archive\pc\content\<nameofarchive>" -o "<outputfolder>"
```

Replace <gamedir> and <outputfolder> with the appropriate desired filepaths.

Once extracted, they can be viewed via [RADTools](http://www.radgametools.com/bnkdown.htm) as Bink Videos and converted to other formats.

## Audio files

[ww2ogg](https://github.com/hcs64/ww2ogg) can be used to convert decompressed archive audio to .ogg through command line, as well as [Revorb](https://cloudflare-ipfs.com/ipfs/QmVgjfU7qgPEtANatrfh7VQJby9t1ojrTbN7X8Ei4djF4e/revorb.exe) (both of these tools have Linux versions that can be found [here](https://www.nexusmods.com/witcher3/mods/6265)) to get smaller and cleaner files that can be played via other media players such as VLC. [ffmpeg](https://ffmpeg.org/download.html) can be used for more convenient playback.

To execute conversion:\
`.\ww2ogg.exe "<!AudioFilePath!>.wem" --pcb packed_codebooks_aoTuV_603.bin`\
_**The argument --pcb is important so as not to return gibberish audio files.**_

It is also recommended to turn down the volume upon playback.

In addition, a combination of these tools can be found at the [Wwise Audio Tools repository](https://github.com/WolvenKit/wwise-audio-tools) which has a command line tool that can be downloaded from the repository or installed through the AUR. It has Linux and Windows support and converts WEM files to OGG without the hassle of the external PCB file or having to run through multiple programs for a clean output.

`./wwtools` converts all WEMs in the current directory to OGG files\
`./wwtools wem [input.wem] (--info)` will convert the specified WEM to OGG and if the optional info flag is used it will print the information about the file and exit.

Playback through ffmpeg:\
`ffplay.exe <!AudioFilePath!>.ogg`\
\
[Foobar2000](http://www.foobar2000.org) can also be used along with its [vgmstream](https://www.foobar2000.org/components/view/foo\_input\_vgmstream) plugin.
