# ECG-Detection-Algorithm
An algorithm built for real-time detection of QRS-complexes in ECG datasets

# Introduction:
The purpose of this assignment is to apply course concepts introduced in class and readings to a real-world application. The first assignment for this course entailed the processing and analysis of an ECG dataset in an effort to develop and test a QRS-complex detection algorithm. In developing the detection algorithm, multiple procedural subtasks were identified, defined, and executed. These subtasks will be expounded upon in the following section discussing background research and the design of the algorithm.

# QRS-complex Detection Algorithm Explained:
## Data preprocessing
Receive and read input from ECG dataset
Remove 8V DC offset
Partition data subset containing first 10 seconds of ECG data for ease of testing
Baseline wander filtering
Filter out baseline wander distortion using a highpass IIR filter with a cutoff frequency of approximately 0.5Hz, using forward-backward IIR filtering to remove the effects of IIR filtering’s non-linear phase response
Powerline interference filtering
Filter out 50-60Hz powerline interference by employing a linear bandstop filter centered at approximately 60Hz
QRS-detection preprocessing
Linear filtering:
Employ forward-backward IIR filtering, introduced in the baseline wander filtering procedure, to enhance the QRS-complex while diminishing the P- & T-waves
Non-linear transformation:
Remove negative component of signal
Square signal
QRS-detection
Find and return peaks timing and amplitudes using an amplitude threshold detector with added heuristics based on peak timing.

This process acted as the basis for the design of the QRS detection algorithm, which was implemented using MATLAB. The complete source code of the algorithm can be found below in Appendix A. With the above-defined steps, implementation in MATLAB was a relatively straightforward process of programmatic implementation. 
