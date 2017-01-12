karmaSoundAnalyser
==================

A Puredata real-time music analysis patch retrieving sensitive information from an audio stream by using various methods. Streams data over a LAN using OSC.  

![Preview](https://raw.githubusercontent.com/Karma-Kusala/karmaSoundAnalyser/master/karmaSoundAnalyser.png)  
_Note: Old screenshot._ [Click here to watch a demo video](https://vimeo.com/84516862)

## Details
__Currently the Pd-Vanilla version works best.__  
 
  Tested on: 
  
- Os X, Pd-Extended 0.43.4 (64 bit) with Aubio 0.4. 
- Os X, Pd-Vanilla 0.46-7 (64 bit) with Aubio 0.4.
- Ubuntu 14.0, Pd-Vanilla (latest) (64 bit), pd-aubio 0.4.

It uses lib Aubio for onset and tempo detection.  
Other features include an alternative onSet detection, pitch detection, silence detection and a 5-band equaliser.  

__Note__: _not all collected data is yet forwarded trough OSC._  

__Note__: _Configure Pd to load aubio on launch or you'll have to open the pd patch twice._  

## Dependencies
  
[Puredata](http://puredata.info/) - The host app for this patch.  
[Aubio Pd plugin](http://aubio.org/pd-aubio/) (v0.4)  

## Installation
### Linux
`sudo apt-get install puredata pd-aubio pd-cyclone`  
add /usr/lib/pg/extra/cyclone to your pb library search paths (from pd preferences)  
Start Pd with `/usr/bin/pd -rt -oss -audiooutdev "2,3,4,5,6" -outchannels "2,2,2,2,2"`.  

Installing Jack on linux can also be useful.  
`sudo-apt-get install jackd qjackctl`  


### Mac OSX
On mac you need [Pd-vanilla 0.46-7](https://puredata.info/downloads/pure-data) (64 bit) and [Aubio](http://aubio.org/pd-aubio/), then it should work out of the box.

Installing [SoundFlower](https://github.com/mattingalls/Soundflower) or [Jack](http://www.jackaudio.org/) can be usefull for routing Audio.


## Thanks
 - Julien Rancoeur ([Fx23](https://soundcloud.com/fx23) / [ADN](http://artdistorsionsnumeriques.com/) )
 - [François Parra](http://www.autotune.eu/)  
 - Clément Sablé( [Nëru](https://neru.io/) )
 
- - - -  
Made for a [Karma Kusala](http://karma-kusala.com/) project.