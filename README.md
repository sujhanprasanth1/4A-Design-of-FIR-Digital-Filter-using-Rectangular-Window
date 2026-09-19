# FIR-FILTER-DESIGN
# EXP 4 A: Design-of-FIR-Digital-Filter-using-Rectangular-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Rectangular-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=Wc/%pi;
else
hd(n)=sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=1;
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR LPF using Rectangular Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR LPF using Rectangular Window');
```
# OUTPUT: 
<img width="712" height="578" alt="image" src="https://github.com/user-attachments/assets/204d594e-663d-40c6-b4a9-27f13da312e8" />
<img width="873" height="503" alt="image" src="https://github.com/user-attachments/assets/40bff5c2-59e7-4e43-9e6d-8060a2a7f4e1" />



# RESULT: 

Thus design of low pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=1-Wc/%pi;
else
hd(n)=-sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=1;
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR HPF using Rectangular Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR HPF using Rectangular Window');
```

# OUTPUT: 
<img width="732" height="578" alt="image" src="https://github.com/user-attachments/assets/04859d5b-066e-4997-9ba5-391ad3de4c36" />
<img width="647" height="653" alt="image" src="https://github.com/user-attachments/assets/9b729305-5d4d-46e5-a39b-fd5abcf25fcc" />



# RESULT: 
Thus design of HIGH pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
Wc2=Wc(2);
Wc1=Wc(1);
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=(Wc2-Wc1)/%pi;
else
hd(n)=(sin(Wc2*((n-1)-alpha))-sin(Wc1*((n-1)-alpha)))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=1;
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR BPF using Rectangular Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR BPF using Rectangular Window');
```
# OUTPUT: 
<img width="730" height="577" alt="image" src="https://github.com/user-attachments/assets/db7fed1a-0e7d-43c7-840a-3a34867d5256" />
<img width="720" height="657" alt="image" src="https://github.com/user-attachments/assets/6acc30c9-a6b0-4a11-92e0-641d9d20441e" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
close;
M=input('Enter the Odd Filter Length =');
Wc=input('Enter the Digital Cut off frequency =');
Wc2=Wc(2);
Wc1=Wc(1);
alpha=(M-1)/2;
for n=1:M
if (n==alpha+1) then
hd(n)=1-((Wc2-Wc1)/%pi);
else
hd(n)=(sin(Wc1*((n-1)-alpha))-sin(Wc2*((n-1)-alpha)))/(((n-1)-alpha)*%pi);
end
end
for n=1:M
W(n)=1;
end
h=hd.*W;
disp(h,'Filter Coefficients are');
[hzm,fr]=frmag(h,256);
subplot(2,1,1);
plot(2*fr,hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR BSF using Rectangular Window');
hzm_dB=20*log10(hzm);
subplot(2,1,2);
plot(2*fr,hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR BSF using Rectangular Window');
```

# OUTPUT: 
<img width="707" height="582" alt="image" src="https://github.com/user-attachments/assets/f7a58d19-3b27-45c0-8dcd-49285d2ab618" />
<img width="757" height="683" alt="image" src="https://github.com/user-attachments/assets/16724c38-a9b3-454a-afaa-5b37423de136" />



# RESULT: 
Thus design of BAND STOP FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

