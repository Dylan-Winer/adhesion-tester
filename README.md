# adhesion-tester

**Description**
Programmed Python application with partner for adhesion testing according to 
ASTM standards by calculating adhesive strength using OpenCV, graphing results 
with Matplotlib, and accepting input with PyQt GUI.

Back-end functionality was developed by myself and Rishabh Kanodia at the High Performance
Materials Institute at Florida State University.

**Research Proposal:**
How can Python and OpenCV be used to develop an application that takes in baseline image and after images from an ASTM D3359 peel test and automatically assign a rating?

**Motivation**
Our motivation for this project came from the desire to create stronger or more specialized materials. Having processes in place to automatically test the quality of a substrate-ink compound would greatly smooth the process. The use of a computer program to rate the materials would also be a lot more accurate than eyeballing the results. Implementing a Python program would also greatly assist the other researchers at the facility, who are testing how sintered materials compare to unsintered, as well as how direction affects the adhesion strength.

**Literature Connection**
There have been many experiments and previous papers written on adhesion tape testing, and we made use of these to refine our procedures and identify what we wanted our program to accomplish. For example, the study by Kovác et al. (2018) helped us to automate the ASTM D3359 adhesion standards by using the proper peel techniques and applying background subtraction to the computer processing of images. Likewise, Zhao et al. (2011) automated the D3359 standards with similar methods but in Photoshop, which is a similar starting principle to using the OpenCV image processing library.

**Materials**
The following materials are required: a roll of clear scotch tape, single-edge razor blade, ruler, sintered and/or unsintered KA802 and CB028 ink, Celestron handheld digital microscope and software, black paper background (formerly black construction paper), and laptop computer.

**Experimental Methodology**
The first step of the procedure is to prepare a sample to be tested. Use a ruler to measure out a 0.75-inch square on a clear glass slide. Cut 4 pieces of clear scotch tape with a single-edge razor blade. Place the tape on the edges of the glass slide around the measured square to properly secure the slide. Put on nylon gloves to avoid contaminating the sample with hand oils. Apply a small ball of ink (should say actual volume later) of KA802 or CB028 to the center of the empty 0.75 in2 square. Use the single-edge razor blade to completely spread the ink to cover the square using smooth consistent motions. 

In the case of unsintered samples, allow the sample to dry in a fume hood for 2-3 hours. In the case of a sintered sample, allow the sample to dry under a heat press for 1 hour. 

Set up the Celestron microscope, ensuring it won’t move during the experiment. When taking images ensure that the image is as focused as possible. Place the finished sample under the microscope, ensuring that the image is centered, focused, and on a black background. Take an initial picture; this will be the baseline which the subsequent photos will be compared to. Slowly let a piece of scotch tape fall onto the sample, ensuring no folds or air bubbles form. Allow tape to rest for 2 minutes. Peel off the tape with a consistent force and angle. Take a second image of the slide after the ink has been peeled off. Take an image of the tape with the removed ink on it.

Use the python program to compare images of peeled-off samples to the base image, which automatically assigns a rating according to ASTM standards.

**Python Program Methodology**
The python program begins by intaking a baseline image (which would be the original sample before the peel test) and the after image (image of slide after peel test). It converts both images to black and white before counting the number of black pixels (background) and the number of white pixels (ink remaining). Using this data, it creates a ratio of the number of changed pixels to calculate how much ink was removed from the sample. It then uses the ASTM standards to automatically assign a quality rating to the sample on a scale of 0-5.

**Results**
The question would be convincingly answered if our program were to be able to accurately rate a picture of the results of an adhesive tape test based on ASTM standards. Additionally, this program would work for every type of ink substrate, regardless of the ink’s color, which we aim to accomplish by standardizing the black background. Moreover, the program would need to give accurate results even when the results border between two ratings, as that would display the program’s superiority as compared to human observation.

The program might be able to pick up on ink particles that the human eye doesn’t notice, which could give unexpected yet possible results. Likewise, the program may not completely differentiate between the ink and the rest of the glass slide, which could give a range of inaccurate results.
