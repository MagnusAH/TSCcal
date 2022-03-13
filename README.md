# TSC Calibrator

Gets the frequency of the TSC so that values from `rdtsc` can be converted to time, much faster than system calls and should work with any compiler (i think).

## Usage

> `tsc_calibrate()`
> Gets the TSC frequency using the default parameters defined in `tsc.c`  
> With default parameters calibration takes a bit over a second.

> `_tsc_calibrate(uint64_t warmup_count, uint64_t sample_count, uint64_t sample_duration, uint64_t deviation)`
> Gets the TSC frequency using the passed parameters.  
> `warmup_count` is the number of the first samples to be used as a warmup (not used for finding the frequency)  
> `sample_count` is the number of samples desired to be used for calculating the frequency  
> `sample_duration` is the duration of each sample in nanoseconds, higher sample duration means higher accuracy, but too high sample duration increases the chance of the process scheduler ruining the sample  
> `deviation` is value representing how tight of a standard deviation should be used for processing the results (higher is tighter)

> `tsc_toNano(uint64_t ticks)`
> returns `ticks` as a number of nanoseconds as a uint64_t

> `tsc_toMicro(uint64_t ticks)`
> returns `ticks` as a number of microseconds as a uint64_t

> `tsc_toMilli(uint64_t ticks)`
> returns `ticks` as a number of milliseconds as a uint64_t

> `tsc_toSec(uint64_t ticks)`
> returns `ticks` as a number of seconds as a uint64_t

> `tsc_toNanoF(double ticks)`
> returns `ticks` as a number of nanoseconds as a double

> `tsc_toMicroF(double ticks)`
> returns `ticks` as a number of microseconds as a double

> `tsc_toMilliF(double ticks)`
> returns `ticks` as a number of milliseconds as a double

> `tsc_toSecF(double ticks)`
> returns `ticks` as a number of seconds as a double
