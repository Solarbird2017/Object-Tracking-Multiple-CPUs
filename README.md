# Object-Tracking-Multiple-CPU
This is the C++ code for object tracking with particle filtering algorithm with adaptive and hybrid techniques.
The filtering algorithm is able to track the objects without training.

1. C++ code for Object Tracking with multiple CPUs, which is verified on a cluster in CUNY High Performance Center.
2. The code was written with MPI interface.
3. hpc_mini, hpc_adaptive, hpc_local, hpc_hybrid refers to different information transfer algorithms between CPUs.
3. The features of the targets can be defined for object tracking.


<p align="center"><img src=https://github.com/Solarbird2017/Object-Tracking-Multiple-CPUs/blob/main/1.png alt="Comparison"></p>
<p align="center"><img src=https://github.com/Solarbird2017/Object-Tracking-Multiple-CPUs/blob/main/2.png alt="Comparison"></p>
<p align="center"><img src=https://github.com/Solarbird2017/Object-Tracking-Multiple-CPUs/blob/main/3.png alt="Comparison"></p>




## usage
The code was tested on Mac and linux platorms.
1. install OpenCV.
2. install OpenMPI
3. export TMPDIR=/tmp
4. mpicxx main.cpp `pkg-config opencv --libs` -w
5. mpirun -np 128 ./a.out 1000  // np: the number of cpus, 128: use 128 CPUs, a.out: executed file, 1000: 1000 particles per CPU.

## Tracking accuracy

The matalb code in ./LabelingMatlabProgram/LabelingGT.m allow you to manually label the targets from a piece of video and save the labeled position of target in a txt file. The C++ program in ./PFTracking_adaptive and ./PFTracking_hybrid can read the txt file and compare it with the estimation position to calculate the accuracy (RMSE error).

## License
The code is released under MIT License (see LICENSE file for details).

