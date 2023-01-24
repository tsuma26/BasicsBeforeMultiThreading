# MutiThreadingInJava
# Before going to start on multithreading

This project is to document few concepts which are important you to understand before starting multi-threading. These concepts help us to create each thread more meaningful. But we will not be going into OS concepts like scheduling. These are just the basics before starting multithreading. Hope this helps.

Any programs you start on your computer is a process (E.g.: word, excel, IntelliJ) all these work as an individual processes.

ASSUMPTIONS: we will consider and discuss about machines that are dual core.

In our machine we can run 2 processes at a time. Thread is a path of execution within a process. Threads exists inside processes. Each processor can run at max 2 threads (main and user defined).
Logical processor = No of CPU processor(in our case 2) * 2

Below diagram shows the single-threaded and multi-threaded processors.
Threads share Memory, in our concern it shares heap memory (now we know why we do synchronization and locking in multithreading). Whereas it has separate Stack for each thread. 

![image](https://user-images.githubusercontent.com/38125917/214294472-0f743313-cfd6-4dbf-85bc-acf50720197e.png)

Multithreading: Allows the execution of multiple parts of program at the same time.
When we start learning multithreading, we come across two terminologies Concurrency and Parallelism. Are they both same?

Concurrency: Execution of multiple threads in overlapping time.  Here no two tasks will run at same time. Below diagram shows that Thread T1, T2 and T3 will never together. They will be picked one at a time. Thanks to the technology, this switching between threads is so fast that we cannot even feel it.
Eg: Concurrency is like our brain which cannot think about two things at a time.

![image](https://user-images.githubusercontent.com/38125917/214297888-f868fed6-390c-420a-bc0d-b7abcba2c318.png)

Parallelism: Dividing problems into sub task which executes in parallel with different threads. Many threads run together. Fork/Join works an example of parallelism.
If we want to implement parallel program, we must specify how problems are subdivided and solutions are combined.

![image](https://user-images.githubusercontent.com/38125917/214298005-46e389b0-9e54-4aba-9ebc-c7b95b7ede3d.png)

Parallel programming has certain limitations:
-> Difficult in implementing in applications that use collections because collections are not thread safe.
-> This might induce Thread interference or Memory consistency error.

Note: In a multithreaded process on a single processor, the processor can switch execution between threads resulting in concurrent execution.
In a same multithreaded process on a multi-processor environment, each thread in the process can run concurrently on separate processor resulting in parallel execution. 

Some questions around what we discussed:
Q1. If single processor can have only two threads, how having multithreading (having more than 2) will help? And Since process context switching is costly how does this happen?
So, the answer is, Thread scheduling is handled by OS threads after JVM. So, OS internally spread the threads across processor using scheduling. Below show
