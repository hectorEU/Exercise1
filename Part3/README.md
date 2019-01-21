# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > *Concurrency means interleaving of different threads/code/processes, serialized in time, whereas in parallelism they happen actually at the same time.*
 
 ### Why have machines become increasingly multicore in the past decade?
 > *There are several resons here:
	1. Power: Power consumption increases non-linearly with voltage, higher frequencies generate more heat to be dissipated, need for low-energy efficient processors (smartphones...)
	2. Speedup: It happens that a process can be many times decomposed in parallel tasks (read keyboard, update screen), and processes can be executed in parallel even without synchronization between them (OS programs, GPU...)
	3. It is more efficient (energy/cost) to use N cores with IPC X than using 1 core with IPC X x N. Moreover, concurrency can cause more overhead due to context switching, cache conflicts*
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > *Multiprocess environment, run OS, ISR handling*
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > *To program proper concurrent programs you have to think them as if the ran in parallel, since there is the same time uncertainity (from the programmer's view) of when things happen*
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > *Processes have their own memory space inside the OS. Threads share memory and managed by the OS, whereas green threads are managed by a virtual machine (such as Java VM) or runtime libraries in case that there is no OS for example. Coroutines are an abstraction of subroutines which allow cooperative multitasking, using the CPU more efficiently than a non-preemptive multitasking (selfish programs).*
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > *pthread_create() -> Threads
    theading.Thread() -> Threads
    go -> Green threads*
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > *When GIL exists, the python Threads behave as green threads since they only yield to one native thread being used concurrently between them*
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > *Multiprocessing*
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > *The GOMAXPROCS variable limits the number of operating system threads that can execute user-level Go code simultaneously*
