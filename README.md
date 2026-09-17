# FIR-FILTER-DESIGN
# EXP 4 A: Design-of-FIR-Digital-Filter-using-Rectangular-Window

# AIM 1:  

To perform Design-of-LOWPASS FIR-Digital-Filter-using-Rectangular-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc ; 

close ; 

M=input('Enter the Odd Filter Length ='); 

Wc=input('Enter the Digital Cut off frequency ='); 

alpha= (M -1)/2 // Center Value 

for n = 1:M 

    if (n ==alpha+1) 
    
        hd(n) = Wc/ %pi ; 
        
        else 
        
        hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
        
    end 
    
end 

for n = 1:M 

    W(n) = 1; 
    
end 

//Windowing filter coefficients 

h = hd.*W; 

disp(h,'Filter Coefficients are') 

[hzm,fr]= frmag (h,256) ; 

subplot(2 ,1 ,1) 

plot(2*fr, hzm) 

xlabel( ' Normalized Digital Frequency w'); 

ylabel( 'Magnitude '); 

title( ' Frequency Response of  FIR LPF using Rectangular Window ') 

hzm_dB = 20* log10 (hzm); 

subplot (2 ,1 ,2); 

plot(2*fr , hzm_dB); 

xlabel( ' Normalized Digital Frequency W' ); 

ylabel( 'Magnitude in dB'); 

title('Frequency Response of FIR LPF using Rectangular Window');


# OUTPUT: 
<img width="1692" height="871" alt="image" src="https://github.com/user-attachments/assets/76648a94-c662-477d-b644-1010fafcffd0" />


# RESULT: 

Thus design of low pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.
