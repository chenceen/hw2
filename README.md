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
Read in data at rate of 1s/sample, Store them in ADCdata[sample]


### 6. Analysis

## Result
```
[['C0A880', 22.34], ['C0F9A0', 18.88], ['C0G640', 20.770000000000003], ['C0R190', 18.339999999999996], ['C0X260', 18.549999999999997]]
```
