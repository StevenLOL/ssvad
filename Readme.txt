This program converts NIST SRE speech files to speech/non-speech segmentation
file in TIMIT .phn format.

Example:


For mic speech:

../bin/sph2phn -sph eslnc.sph -phn eslnc_A.phn -ch A -dn Y -df eslnc_A.wav -af 0.95
../bin/sph2phn -sph ftvhv.sph -phn ftvhv_A.phn -ch A -dn Y -df ftvhv_A.wav -af 0.95

If you find that the denoise wave file contains pulses, you may set -fs to 1024.

For clean tel speech, you may disable denoising (-dn N) and set -af to 0.99.

For technical details, visit the SSVAD site in my homepage and download the papers of SSVAD:
http://bioinfo.eie.polyu.edu.hk/ssvad/ssvad.htm


Man-Wai MAK



#TO BUILD
0) Due to copyright issues, the files "fft.c" and "fft.h" have been excluded from the compressed file. 
If you want to compile the program, please contact enmwmak at polyu.edu.hk 
1) download and install The [NIST SPeech HEader REsources (SPHERE) Package Version 2.7](http://www.nist.gov/itl/iad/mig/tools.cfm)
1.1) you many need to del "-m32" in makefile 
1.2) you many need to swap "-lm" to the end of the LLIBS
eg:
LLIBS	= -l$(COMBINEDLIB) -lm

2) and set ./src/Makefile:NISTDIR= your nist PATH
3) cd src and make

