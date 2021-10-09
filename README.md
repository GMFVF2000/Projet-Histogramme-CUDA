1)  Using Cuda itself is first of all a challenge because I have never done parallel programming. So I notably had the opportunity to write the code and be able to separate the different operations to perform.

2) The optimization of the code and that the memory accesses, the conditional instructions in the kernel as well as the maximization of the occupation of the GPU were an absolute advantage in the process of optimizing the histogram.

3) We can cite two global readings, first of all, following the allocation of the GPU memory, we will make a copy on the GPU of the input memory which will activate the launch of the Kernel with a copy of the output memory on the GPU. To finish this global reading we will have a copy of the GPU memory to the CPU which will be the basis of the basis of the release of the GPU memory in order to check the accuracy of the information collected.

4) For my program I had to make a histogram with 128 bins considering the ASCII character of the task to be accomplished. The histogram boxes are unsigned 32 bit counters which do not saturate. Each character, except the 36 and 42, is mapped in its own bin for a fixed total of 68 bins

5)  With the blockIdx.x command I allocate memory on the GPU, CudaFree can also solve the problem. The implementation of an excellent compiler and Threads in my programs will allow to avoid conflicts as much as possible.
