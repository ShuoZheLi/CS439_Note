#### What is process
##### what process is?
* program = static file (image)
    * ```process  = executing program = program + execution state```
* A **process** is the **basic unit of execution** in an OS 
* **Different processes** may run **different instances** of same program
* process execution requires:
    * memory contain program code(code segment) and data(other segment)
    * CPU registers
&nbsp;
0x12345
![process's address space](https://github.com/ShuoZheLi/MarkDownPhotos/blob/master/process's%20address%20space.PNG?raw=true "process's address space" )
0x00
&nbsp;
![allocated_process_data_into_physical_memory](https://github.com/ShuoZheLi/MarkDownPhotos/blob/master/allocated_process_data_into_physical_memory.PNG?raw=true "allocated_process_data_into_physical_memory")

##### process state
* contents of address space
    * code or instructions
    * static data
    * stack (including program's call chain)
    * heap (dynamic data is allocated)
* registers and their contents
    * heap pointer
    * program counter: indicate where next instruction is
    * stack pointer
* open file table, set of OS resources in use
* process identifer (PID) ```Unique ID of each process```
* process execution state (ready, running)

##### **process life cycle**
![process_life_cycle](https://github.com/ShuoZheLi/MarkDownPhotos/blob/master/process_life_cycle.jpg?raw=true "process_life_cycle")



##### how does OS track a process
* OS uses _**Process Control Block**_ (PCB)
    * is a Dynamic kernel data structure kept in memory
    * PCB = execution state + location of each process when not executing
* PCB contains
    * PID + program counter + stack pointer + registers' content + heap pointer(memo manage info), username, open file table, any execution state not stored in the address space
``` PCB initialized when process is created, deleted when process terminates```
**when process run from blocked states, registers will get value from PCB and continue to run the rest of the program**
##### what is static variable
```C
static int x = 2;
// static variable is declared inside of function but exist throughout the life of the program
// it can be declared every where in the program
```
```static variable in static data segment```
So, not like stack variable that will get reset each time