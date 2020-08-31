#### History of Operating Systems
##### Phase 1: Expensive Hardware, Cheap Humans
1. One user on the console, one process at a time.
    * Porgram by wires and stack of cards
    * during inputing, cpu is idle
2. Batch processing: load program, run, output (sperate IO and CPU)
    * advantages
        * next job can be loaded immediately after the prev one finished
    * disadvantages
        * No protection-- bug program can crash the batch monitor
        * cpu is idle during IO
3. Overlap of IO and computation, interrupts
    * OS request IO, doing computing while waiting, get interrupt when IO finishes
    * Add concurrency within same process (IO and computing)
    * No sharing, **_only protect OS from application_**
    * buffering and interrupt handling in OS
4. Multiprogramming: several programs run at same time sharing machine
    * One jobn runs until it perform IO, then another job gets the CPU
    * Scheduler manage interactions between concurrent programs (protection betwee, which one start and execute)
    * Requires: **_Memory protection and relocation_**
![multiprogramming](https://github.com/ShuoZheLi/MarkDownPhotos/blob/master/multiprogramming.PNG?raw=true "multiprogramming")
&nbsp;
&nbsp;
##### Phase 2: Cheap Hardware, Expensive Humans 
（**Interactive Timesharing**）
(problem before, users or programmers wait long time for output)
5. Interactive Timesharing
    * many terminals for multiple users to use the system
        * debug easier
        * porgram stop and start by schedule more frequently to give illusion you are the only one using computer
    * more sharing, more protection, more concurrency
    * new OS services: shell, file system, rapid process switching (user can interact), _**virtual memory**_ (processes running simultaneously)
    * new problems: trashing (over use of memory), response time
![timesharing](https://github.com/ShuoZheLi/MarkDownPhotos/blob/master/timesharing.PNG?raw=true "timesharing")
&nbsp;
&nbsp;
##### Phase 3: Very Cheap Hardware, Very Expensive Humans 
6. Personal Computing
    * simplify OS by eliminating multiprogramming, concurrency, and protection
        * failed: humans are expensive, programs cannot crash each other
7. Parallel and Distributed Computing
    * Parallel System: multiple processors are in same machine, share memory, IO devices......
    * Distribute System: multiple processors communicate via network
    * Advantage: increase performance, increase reliability, sharing of specialized resources

