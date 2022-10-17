# Operating System

Created: September 24, 2022 2:17 PM
Reviewed: No

Application software performs specific task for the user.

System software operates and controls the computer system and provides a platform to run
application software.

eg. Windows Ubunbtu mac, compilers

An operating system is categorised as a System software that serves as an interface between users and computer hardware This  performs the most basic tasks of memory management , process management, handling i/o , and managing devices like printers.

An operating system function -

- Process management,
- resource management
- memory management
- storage management
- security and privacy
- 

![Untitled](Operating%20System%20fa0e2c1964344047bec3c24e349ec77d/Untitled.png)

Types of OS:

1. Batch Os
- We used Punch Cards → Tasks were hard coded on them → similar kind of jobs were batched together by the operator and results were given out later
- Next task starts only after completing first task
1. Multi Programming Vs Multi Tasking

| Multi program | Multi tasking |
| --- | --- |
| Idleness decreases  | Responsiveness increase |
| eg. 10 students  + 5 questions each- We will solve all questions of std1 then move to std2. meanwhile if he goes to washroom then we move to std2 early | eg. We solve 1 Q of std1 then go to std2 , then solve 1 Q then go to std3 and so on. |

Process Stages

Preamitive/Non Preamitive=  having/not having prioty/time quantum line

![Untitled](Operating%20System%20fa0e2c1964344047bec3c24e349ec77d/Untitled%201.png)

**SYSTEM CALLS**

1. fork()
- 

![Untitled](Operating%20System%20fa0e2c1964344047bec3c24e349ec77d/Untitled%202.png)

**Process Vs Threads**

![Untitled](Operating%20System%20fa0e2c1964344047bec3c24e349ec77d/Untitled%203.png)

Revise: Kernel Level Threads Vs. User Level Threads

## →II. CPU Scheduling

---

Non-Preemptive: When a Process P1 moves from Ready queue to running queue , then unless its completed , no new Process P2 is worked .

Preemtive : When a Process P1 moves back from Ready Queue to Running Queue, then that is called Preemtive.

 **Reasons for preemtion:** 

1.  High Priority Process Arrives
2. Time Quantum: I.e. process takes longer to finish than the time assigned by CPU

![Untitled](Operating%20System%20fa0e2c1964344047bec3c24e349ec77d/Untitled%204.png)

Arrival Time: The POINT of time when a process enters a Ready Queue(kitne baje)

Burst Time: The duration of time a process takes to get completed in CPU

Completion Time : The POINT of time at which process completes 

Turn Around time: Completion time- Arrival time ( We enter bank at 11am = AT and transaction takes 15 min= BT, and we come out at 12pm= CT, so TAT= 12-11 = 1hr.)

Waiting time= TAT- BT= (45 min)

Response time= (Point of time at which we first meet CPU- AT)

→ **Nonpeemtive:**

1. FCFS⇒ Criteria= AT
2. SJF⇒ Criteria= BT

→ **Preemptive**

1. Shortest Remaining TF ⇒ SJF with **Preemption** ⇒ Criteria BT
2. RR⇒ Preemptive ⇒ Criteria = Time Quantum

## →III. Process Synchronisation

---

Process → 1. Cooperative 2. Non Cooperative

Cooperative share Memory, Data, Code, Resource and can give faulty output due to **Race Condition :viz P1 and P2 try to use Critical section simultaneously  here the shared = 5 (right ans.)**

![Untitled](Operating%20System%20fa0e2c1964344047bec3c24e349ec77d/Untitled%205.png)

4 conditions for Entry Condition:(MPB-H)

- **Mutual Exclusion: Two process cant be in critical section simultaneously**
- **Progress: P1 doesn’t interfere with P2 (general society example)**
- Bounded Wait: Process P1 takes it turn then let P2 use the CPU(One guy takes a Job offer , then takes the second Job Offer, then the third… while other just  waits. This needs to stop)
- No assumption related to H/W speed : No limitations regarding LInux, Windows , Mac. solution needs to run on every machine

**Lock Variable**

lock=1 ⇒ Process in CS and Vice-versa

A process can enter CS when LOCK=0→ Once it enters, it sets LOCK=1 → once it leaves the CS ,it sets LOCK=0

**Test and Set** : EASY revise→ Achieves Mutual exclusion and Progress 

**Turn Variable** :This achieves Mutual Exclusion, No Progress though, Achieves Bounded wait, and is OS independent.

![Untitled](Operating%20System%20fa0e2c1964344047bec3c24e349ec77d/Untitled%206.png)

**→ Semaphore:** 

- Int Value
- Used for ME
- synchronises processes

Note :to enter the CS run the  P /wait/down code and vice-versa

Type I.  Counting Semaphore (-inf to +inf) 

| P/  wait / down | V/signal/ up |
| --- | --- |
| Down(Semaphore S) | Up (Semaphore S) |
| S - -  | s++ |
| if(s < 0) | if(s ≤ 0) |
| Send the process to sleep | Wake a process |
| else |  |
| return |  |

Up : 

- Increases s value
- wakes up a process from suspend list

Down:

- Decreases s value.
- Sends process in critical section

Type II. Binary Semaphore 

Down→ 

1 to 0 (successful operation)

0 to 0 (unsuccessful operation)

Up→

0 to 1 (successful operation)

1 to 1 (unsuccessful operation)

Mutex= 1key/ 2 people / 1 toilet

Semaphore= 2 key/ 3 people / 2 toilet

![Untitled](Operating%20System%20fa0e2c1964344047bec3c24e349ec77d/Untitled%207.png)

## →III. Deadlock

---

If 1+ processes occur simultaneously in such a way that they interfere with the progress of other processes , because each process is holding a resource and waiting for another resource acquired by some other process. that is called as deadlock 

4 conditions of deadlock: (MNC - Hyderabad)

- Hold and wait (Resources should be non sharable)
- Circular wait
- No preemption
- Mutual exclusion

Use **RAG** to predict if there exists a deadlock then use one of 4 Methods  to prevent Deadlock:

- Ostrich method- simply ignore the deadlock
- Dead lock prevention - Make 1+ /4 conditions of deadlock (MNC- Hyderabad) false
- Banker’s algo (detection  + avoidance)
- Deadlock detection and prevention

## → IV. Memory Management

---

  

![Untitled](Operating%20System%20fa0e2c1964344047bec3c24e349ec77d/Untitled%208.png)

I .**Contiguous Partition:** 

- FIXED/STATIC partition

 We fix the number of partitions , but the size of the partitions can be same( called fixed partition) or different(variable partition)

Note: What’s internal fragmentation?

→ In contiguous memory allocation when a smaller (2 Mb) process occupies a bigger Ram Partition of (8 mb)

What’s External Fragmentation?
→ In Contiguous memory allocation , when a process(5MB) comes to RAM that has enough free space (6MB) but its not accommodated due to lack of singularity of space. 

- VARIABLE/ DYNAMIC partition