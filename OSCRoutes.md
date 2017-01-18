# karmaSoundAnalyser

## OSC addresses
All OSC addresses are prepended with `/kmsa`.

### Output
The following MIR variables are streamed over OSC.

| Address      | Type           | Range       | MIR Description |
| :---         |     :---:      | :---        | :---            | 
| __Balance__                                                ||||
| /balance     | float       | -1.0 to 1.0 | Balance between left and right audio channels. |
| /balanceAmpL | float       | 0.0 to 1.0  | Amplitude of the left audio channel.|
| /balanceAmpR | float       | 0.0 to 1.0  | Amplitude of the right audio channel. |
| __Aubio__                                                     |
| /aubioIsPlaying   | bool      	  | true / false     | Indicates if there's audio playing. |
| /aubioIsQuiet     | bool      	  | true / false     | Indicates if there's silence. |
| __Metronom__                                                  |
| /metronomTick       | bang   |            | A notification on every tick. |
| /metronomTickNum    | int    | 0 to 3_*_  | Tick number. 0 is the accented tick.<br> _*_ The metronom's accent defines the number of ticks. |
| /metronomAccentTick | bang   |            | A notification on the metronom accent tick (Same as tick #1). |
| /metronomCycles     | int   | 0 to &infin;| Number of cycles detected, increments every 4_*_ ticks.<br>_*_Based on `accent` default value: 4. |
| /metronomBPM        | int   | 0 to ±200   | Currently estimated BPM. |
