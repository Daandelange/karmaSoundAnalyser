karmaSoundAnalyser
==================

A Puredata real-time music analysis patch retrieving humanly sensitive information from a live audio stream by using various methods.  
Streams [Music Information Retrieval](https://en.wikipedia.org/wiki/Music_information_retrieval) data over a LAN using [OSC](https://en.wikipedia.org/wiki/Open_Sound_Control).  
Pure Data is multiplatform, as is this patch: Linux, Mac & Windows.  

![Preview](https://raw.githubusercontent.com/Karma-Kusala/karmaSoundAnalyser/master/karmaSoundAnalyser.png)  
_Note:_ [Click here to watch an older demo video](https://vimeo.com/84516862)

## Details   
karmaSoundAnalyser is divided into several `.pd` abstractions, each one handling the analysis of a particular musical aspect.  
This Pure Data patch uses lib Aubio for onset and tempo detection.  
Other features include an alternative onSet detection, pitch detection, silence detection, a 5-band equaliser, note detection, etc.  

For a full list of MIR data, please refer to the [OSC addresses table](https://github.com/Karma-Kusala/karmaSoundAnalyser/blob/master/OSCRoutes.md).

__Note__: _Not all collected data is yet forwarded trough OSC._  

__Note__: _Configure Pd to load Aubio on launch or you'll have to open the pd patch twice._  

## Dependencies  

- [Pure Data](http://puredata.info/) `v0.47-1-64bit` - The host app for this patch.  
- [Lib Aubio Pd plugin](http://aubio.org/pd-aubio/) `v0.4`  - A Pd plugin for detecting tempo and more.
- Recomended: A __wired__ LAN for better performance.
- Optional: MrPeach Pd externals.

----
## Installation

### Linux
`sudo apt-get install puredata pd-aubio pd-cyclone pd-mrpeach`  
add /usr/lib/pg/extra/cyclone to your pb library search paths (from pd preferences)  
Start Pd with `/usr/bin/pd -rt -oss -audiooutdev "2,3,4,5,6" -outchannels "2,2,2,2,2"`.  

Installing Jack on linux can also be useful for routing audio.  
`sudo-apt-get install jackd qjackctl`  

### Rpi
Follow the Linux installation notes.
Feel free to add additional setup notes in a pull request. :-)

### Mac OSX
On mac you need [Pd-vanilla 0.47-1-64bit](https://puredata.info/downloads/pure-data) and [Aubio 0.4](http://aubio.org/pd-aubio/), then it should work out of the box. Later versions should also work.  

__Optional__: You can install the MrPeach externals via: Pd < Help < Find Externals, then type `mr peach` and install it.

__Hint__: _To get started quickly, use [VLC](http://www.videolan.org/) to play a track and output it trough [SoundFlower](https://github.com/mattingalls/Soundflower) (2ch), then set the Pd sound input to Soundflower accordingly. Alternatively use [Jack OSX](http://www.jackaudio.org/) to route audio._  

### Windows
Sorry, windows is yet untested but there's no reason it won't work.  
Feel free to add setup notes in a pull request. :-)

----
## Run
Simply open `karmaSoundAnalyser-PdVanilla.pd` with Pure Data.  
You can _right click_ < _open_ each abstraction to see what's happening within.  
I recommend reading [the Pd Floss Manuals](http://write.flossmanuals.net/pure-data/introduction2/) if you're not familiar with Pd. ( [French version here](https://www.flossmanualsfr.net/puredata/) )

----
## Thanks
 - Julien Rancoeur ([Fx23](https://soundcloud.com/fx23) / [ADN](http://artdistorsionsnumeriques.com/) )
 - [François Parra](http://www.autotune.eu/)  
 - Clément Sablé( [Nëru](https://neru.io/) )  
 
----  
Made for a [Karma Kusala](http://karma-kusala.com/) project.