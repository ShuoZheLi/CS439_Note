#### Three roles of operating system
##### referee
* Manage shared resources
    * coordinate multiple apps and users to have efficiency 
* Isolation
    * protect process from each other
* Communication
    * helpe process(进程) to work together

##### illusionist
* illusion of resources that not really present
    * Virtualization: more processors, memory, screen space, run many apps at once! Actually not!
    * entire computer

##### Glue
* provide interface to hardware
    * File system (no need to tell where to save data on disk), Virtual memory, networking 


&nbsp;
#### Evaluating an operating system
##### realiability
* OS does exactly what designed to do
* should be bug free in theory
* Availability: % of time system is useful

##### security
* OS cannot be compromised by a malicious attacker
* Security policy
* Enforcement mechanism (used to enforce policy)
* Strong fault isolation help, but need also need to share

##### portability
* OS does not change as hardware changes
* OS can support apps not yet written
* working on 3 interfaces
    * AMI (abstract machine interface)
        * between OS and apps = API + memory access model + legal executable instructions
    * API (application programming Interface)
    * HAL (Hardware Abstruction layer)
        * abstracts hardware internally to the OS 
![layers_in_OS](https://github.com/ShuoZheLi/MarkDownPhotos/blob/master/layers_in_OS.PNG?raw=true "layers_in_OS")

##### Performance
* Efficiency/Overhead
    * how much lost by not running on bare hardware(how much resource taken by OS)
* Fairness
    * How are resource divided
* Response time
    * how long does a task take to deliver a response to user
* Throughput (measure not interactive computer)
    * how many task complete per unit of time
     (_do not compare OS with OS that is running firefox_)
* Predictability
    * are the performance metrics consistent over time?
    * predictable, do not want to slow down or fast



