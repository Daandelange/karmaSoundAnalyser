# karmaSoundAnalyser

## OSC addresses
All OSC addresses are prepended with `/kmsa`.

### Output
The following MIR variables are streamed over OSC.

| Address      | Type           | Range       | MIR Description |
| :---         | :---           | :---        | :---            | 
| __Balance__                                                ||||
| /balance/pan  | float       | -1.0 to 1.0 | Balance between left and right audio channels. |
| /balance/ampL | float       | 0.0 to 1.0  | Amplitude of the left audio channel.|
| /balance/ampR | float       | 0.0 to 1.0  | Amplitude of the right audio channel. |
| __Aubio__                                                     |
| /aubio/isPlaying   | bool  | true / false  | Indicates if there's audio playing. |
| /aubio/isQuiet     | bool  | true / false  | Indicates if there's silence. |
| /aubio/attack      | bang  |               | Onset / attack event notifier. |
| /aubio/tempo       | bang  |               | Tempo detection. Sends beat events. |
| /aubio/tempoAlt    | bang  |               | Detects an alternative tempo. |
| /aubio/pitch       | int   | 0 to &infin;  | Tries to detect a dominating pitch, sends it's value (in Hz) if found, otherwise 0. |
| /aubio/zcr         | float | 0.0 to 1.0    | Zero crossings rate. |
| /aubio/transients  | float | 0.0 to 1.0    | Transients treshold. Transients indicate unstable sound signals or newly introduced sound signals. |
| /aubio/steadyState | float | 0.0 to 1.0    | Steady-state treshold. Indicates stable sounds that remain over time.  |
| __Metronom__                                                  |
| /metronom/tick       | bang   |             | A notification on every tick. |
| /metronom/tickNum    | int    | 0 to 3 _*_  | Tick number. 0 is the accented tick.<br> _*_ The metronom's accent defines the number of ticks. |
| /metronom/accentTick | bang   |             | A notification on the metronom accent tick (Same as tick #1). |
| /metronom/cycles     | int    | 0 to &infin;| Number of cycles detected, increments every 4 _*_ ticks.<br> _*_ Based on `accent` default value: 4. |
| /metronom/BPM        | int    | 0 to ±200   | Currently estimated BPM. |
| __Fiddle__                                                    |
| /fiddle/attack      | bang  |             | A notification on every beat. |
| /fiddle/pitch       | int   | 0 to &infin;  | Tries to detect a dominating pitch, sends it's value (in Hz) if found, otherwise 0. |
| /fiddle/pitchRaw    | int   | 0 to &infin;  | Same as above but updated more frequently. (_update rate 150Hz max_) |
| /fiddle/amp         | float | 0.0 to 1.0    | Amplitude of audio signal. |
| /fiddle/ampRaw      | float | 0.0 to 1.0    | Same as above but updated more frequently. (_update rate 150Hz max_) |
| /fiddle/silence     | bang  | true / false  | Turns true after 2 secs of silence. |
| __Notes__                                                    |
| /notes/1 (to 7)      | array  |             | Frequently detected notes. Sends an array of: [ID, amplitude, frequency, change flag] |