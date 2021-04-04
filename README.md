# Homework 2 Digital, Analog I/O, and LCD
Select fre


## How to setup and run the program
### 1. Inpot button
Input three buttons to choose frequency, up, down, and confirm.
Up, and down buttons as InterruptIn, confirm as DigitalIn.
```
InterruptIn upbtn(D3);
InterruptIn downbtn(D4);
DigitalIn confirm(D5);
```

### 2. Display
First display the frequency that can be selected.
Create a triangle to point to the selected frequency. 
As upbtn pressed, move to higher frequency. As downbtn pressed, move to lower frequency. 
After confirm button pressed, deliver the selected frequency to the function for generating waveform.


### 3. Generate waveform
Genrerate the triangular wave at selected frequency, and S equals to mod10(1+0+7+0+6+1+1+1+5) = 2
Using thread to run in the same time as  other function.
Construct two loops with delay, one for upcounting, and the other for down counting. Let index of loop increase with specific rate to set the waveform at selectic frequency.


### 4. Measure
Connect picoscope to the ouput of generated waveform (after the RC filter).


### 5. Sample
Read in data at rate of 1s/sample, Store them in ADCdata[sample], and print it.


### 6. Analysis
Create a new code to analysis
```
code FFT.py
```
Read an echo string from B_L4S5I_IOT01A terminated with '\n', store the value in y[x] at x=0 to sample.
Using fft computing and normalization to find absolute value of Y respect to frequency.
Plot two plots, one with amplitude respect to t, and the other with absolute value of Y respect to frequency.

### 7. Run the program
```
sudo mbed compile --source . --source ~/ee2405/mbed-os-build/ -m B_L4S5I_IOT01A -t GCC_ARM -f

```
view the plot
```
sudo python3 FFT.py 
```
View the waveform measure by picoscope
```
picoscope &
```
View the ADCdata[] value
```
sudo screen /dev/ttyACM0
```

## Result
1Hz

<img width="500"  src="https://github.com/chenceen/hw2/blob/main/hw2_1hz_wv.png"/>
<img width="500"  src="https://github.com/chenceen/hw2/blob/main/hw2_1hz.png"/>

185Hz

<img width="500"  src="https://github.com/chenceen/hw2/blob/main/hw2_185hz_0.1swv.png"/>
<img width="500"  src="https://github.com/chenceen/hw2/blob/main/hw2_185hz_5mswv.png"/>
<img width="500"  src="https://github.com/chenceen/hw2/blob/main/hw2_185hz.png"/>

400Hz

<img width="500"  src="https://github.com/chenceen/hw2/blob/main/hw2_400hz_0.1swv.png"/>
<img width="500"  src="https://github.com/chenceen/hw2/blob/main/hw2_400hz_2mswv.png"/>
<img width="500"  src="https://github.com/chenceen/hw2/blob/main/hw2_400hz.png"/>
