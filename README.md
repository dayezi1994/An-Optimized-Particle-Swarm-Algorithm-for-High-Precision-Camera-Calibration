![image](https://github.com/user-attachments/assets/7a694795-4822-4e3c-8ee6-5484ceeb95dc)![image](https://github.com/user-attachments/assets/b2652096-53db-42bf-b0cb-c6456305a52e)

This is the code repository for "An Optimized Particle Swarm Algorithm for High-Precision Camera Calibration with Enhanced Wide-Angle Distortion Correction".

It includes the core code of the paper, point cloud testing program, and testing data.

Due to its large size, please visit the following link to view the code for section "CalibrationWizard-new".

CalibrationWizard-new.zip

https://pan.baidu.com/s/1xB436zuCzCGj-MrmrgI0nQ

Extract code: zy43 

![image](https://github.com/user-attachments/assets/fa7b9b76-d833-41ab-98b3-85cd8d18dfa7)

![image](https://github.com/user-attachments/assets/e8e46ef9-596d-49df-91b0-de34be5fd4cb)

![image](https://github.com/user-attachments/assets/4134a026-00e0-4100-81fb-47719232514d)


If you find our code or paper useful, please consider citing

@inproceedings{
 author =  {Qingqing Ji, Zhaoxin Li, Min Shi, Mingdeng Zhu, Qiao Duan and Zhaoqi Wang},
 title = {An Optimized Particle Swarm Algorithm for High-Precision Camera Calibration with Enhanced Wide-Angle Distortion Correction},
 booktitle = {The Visual Computer},
 year = {2025},
}

Requirements
Microsoft Visual Studio 2019
OpenCV
MATLAB

Tested working on windows 7, OpenCV 2.4.11 and MATLAB R2015b.

First step: run binary ./bin/CalibrationWizard and choose mode=0 to capture images freely for initial calibration. Press space to capture one image. After capturing, press ESC and the calibration is automatically done.
Second step: run src_matlab/main_estimate.m to estimate the next best pose.
Third step: run binary ./bin/CalibrationWizard again and choose mode=1. The estimated next pose should be displayed. You can try to overlay the checkerboard with the new pose, and press space to capture the image.
Loop over the second and third step until you are satisfied, or tired :)



mode=0 captures images for initial camera calibration
mode=1 shows the next best pose for capturing
In addition, we provide mode=2 if you only want to perform calibration on all the captured images listed in out/images/image_list.xml.



Release codes of the unified system in C++ which integrates the next best pose estimation.
Extreme Poses
Sometimes the next pose is extreme so the checkerboard cannot be detected. Please consider:


Check if the values in the uncertainty map are low. If yes, then the calibration has more or less converged.
Consider autocorrelation matrix, simply set autoCorr_flag=1 in src_matlab/main_estimate.m.
Re-run src_matlab/main_estimate.m.


