# Digital-Signal-Processing--FIR-BAND-STOP-FILTER-DESIGN

## AIM:
To generate design of Band Stop FIR digital filter using Window.

## Software Required:
MAT LAB R2012.

## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Band Stop filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 

```
clc; % clear screen
clear all; % clear screen
close all; % close all figure windows
wc1=input('enter the value of wc1');
wc2=input('enter the value of wc2');
N=input('enter the value of filter');
alpha=(N-1)/2;
eps=0.001;
%Band Stop Filter Coefficient 
n=0:1:N-1;
%hd=(sin(wc2*(n-alpha+eps))-sin((n-alpha+eps)*wc1))/(pi*(n-alpha+eps))
hd=(sin(pi*(n-alpha+eps))-sin((n-alpha+eps)*wc1)+sin((n-alpha+eps)*wc2))./(pi*(n-alpha+eps)) 
%hd=(sin(wc1*(n-alpha+eps))+sin(pi*(n-alpha+eps))-sin((n-alpha+eps)*wc2))/(pi*(n-alpha+eps)) 
%Bartlett Window Sequence
n=0:1:N-1;
wh=0.54-0.46*cos((2*pi*n)/(N-1))
hn=hd.*wh
% Plot the Low Pass Filter with Bartlett Window Technique
w=0:0.01:pi;
h=freqz(hn,1,w);
plot(w/pi,abs(h),'blue');
 
```

## OUTPUT:
![4bf78a20-61dd-419c-a20e-6c30705ede8e](https://github.com/user-attachments/assets/2fb34a9d-6ffd-4ba5-8b8a-59fe501e7229)




## RESULT:
![80d0845f-4118-4d78-9bd7-d58eff942a6b](https://github.com/user-attachments/assets/237be8ba-5ccd-4e6c-8c25-87ac497e1904)



