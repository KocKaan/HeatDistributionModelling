# HeatDistributionModelling

Using OpenMP this code parallelizes the sequential heat distribution model.
The temperature at an inside point is calculated as the average of the temperatures of the four neighboring points.
The edge points are when i = 0, i = n-1, j = 0, or j = n-1, and have fixed values corresponding to the fixed temperatures of the edges.


The compilation command is:
gcc -Wall -std=c99 -fopenmp -o heatdist heatdist.c -lm

You run the code with ./heatdist x y z k where x is the dimension of the 2D array, y is the
number of iterations and z can be 0 (runs and measures the time of the sequential version) or 1 (run the OpenMP version when you finish it and measure the timing), and k is the number of threads for the OpenMP version. Note that even if you try with z = 0 (i.e. sequential version) you have to type a number for k. Otherwise, the program will exit.


Be careful: when you run your OpenMP version (i.e. z= 1) the code will take long time because it will run both the sequential and parallel in order to compare the results for correctness. It will measure the time of the parallel version only.
