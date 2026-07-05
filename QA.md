# OS Theory — Easy Q&A Guide (No Numericals)

Simple, exam-ready answers for all your topics. Each answer is short, in plain language, with an example where it helps.

---

### 1. What is an Operating System (OS)?

An OS is software that sits between **you (the user)** and the **computer hardware**.

It manages the CPU, memory, files, and devices so you don't have to deal with the hardware directly.

**Example:** Windows, Linux, Android.

---

### 2. Functions of OS

1. **Process Management** – starts, runs, and stops programs.
2. **Memory Management** – decides which program gets how much memory.
3. **File Management** – lets you create, save, and delete files.
4. **Device Management** – controls hardware like printer, mouse, keyboard.
5. **Security** – blocks unauthorized access.

---

### 3. Objectives of OS

1. **Convenience** – make the computer easy to use.
2. **Efficiency** – use hardware resources well, don't waste them.
3. **Ability to Evolve** – allow new features to be added easily later.

---

### 4. Operating System Structure

| Structure | Simple Meaning |
|---|---|
| **Monolithic** | Whole OS is one big program. Fast, but hard to fix/update. |
| **Layered** | OS is built in layers, each layer only talks to the layer below it. Easier to debug. |
| **Microkernel** | Only the most essential stuff stays in the kernel; everything else runs outside it. More secure. |
| **Modular** | Core kernel + extra features added as separate modules (like plugins). Used in Linux/macOS. |

---

### 5. System Call

A **system call** is how a program asks the OS to do something for it — like open a file or create a new process.

**Why needed?** Programs aren't allowed to touch hardware directly (for safety). So they "call" the OS, and the OS does the risky part safely.

**Example:** `open()`, `read()`, `write()`.

---

### 6. Process

A **process** is a program that is currently running.

**States a process goes through:**
```
New → Ready → Running → Terminated
              ↕
           Waiting
```

- **New** – being created
- **Ready** – waiting for CPU
- **Running** – actually executing
- **Waiting** – paused for I/O or some event
- **Terminated** – finished

---

### 7. Context Switching

Context switching = the CPU **stops one process and starts another.**

Before switching, the OS **saves everything** about the current process (so it can resume later exactly where it left off).

**Downside:** switching takes time where no real work happens — this is called **overhead**.

---

### 8. PCB (Process Control Block)

PCB is like an **ID card** the OS keeps for every process.

**Contains:**
- Process ID
- Process state (running/waiting/ready)
- Program counter
- CPU registers
- Memory info
- I/O info

Used whenever the OS needs to pause and resume a process.

---

### 9. Starvation

Starvation = a process **never gets the CPU** because other processes keep jumping ahead of it.

**Example:** In priority scheduling, a low-priority process may wait forever if high-priority processes keep arriving.

---

### 10. Aging

Aging = slowly **increasing the priority** of a process the longer it waits.

This fixes starvation — eventually the waiting process becomes "high priority" and gets its turn.

**Simple way to remember:** the longer you wait in line, the more "important" you become, until you're served.

---

### 11. Multiprogramming

Multiprogramming = **many programs stay in memory at once**, so the CPU always has something to do.

**Goal:** keep the CPU busy — don't let it sit idle just because one program is waiting for I/O.

---

### 12. Multitasking

Multitasking = the CPU **switches between programs so fast** that it feels like they're all running at the same time.

---

### 🔑 Diff: Multiprogramming vs Multitasking

| Multiprogramming | Multitasking |
|---|---|
| Goal is to keep CPU busy | Goal is to give fast response to users |
| Switches only when a process needs I/O | Switches after a fixed time slice, even if process could continue |
| User may not feel multiple things happening | Feels like everything is happening at once |

---

### 13. Basic Architecture of Computer System / OS

```
        Users
          │
   Application Programs
          │      (System Calls)
    Operating System
 (Process | Memory | File | Device Management)
          │
    Computer Hardware
   (CPU | Memory | I/O | Storage)
```

- **Hardware** – the physical parts (CPU, RAM, disk).
- **OS** – manages the hardware, sits right above it.
- **Applications** – programs users actually open (browser, games, etc.)
- **Users** – interact with applications, never touch hardware directly.

---

### 14. IPC (Inter-Process Communication)

IPC = how **different processes talk to each other and share data**.

**Why needed?**
1. Sometimes processes need to **share information**.
2. Splitting a big task into smaller processes is **faster**, but they need to talk to combine results.
3. Makes the system **easier to manage** — small processes doing specific jobs.

**Two main ways:** Shared Memory, Message Passing.

---

### 15. Race Condition

A **race condition** happens when two processes access the same shared data at the same time, and the result depends on **who goes first** — leading to wrong or unpredictable answers.

**Example:**
Two threads both try to increase a shared variable `count = 5` at the same time:

```c
// Both threads read count = 5 before either writes back
Thread A: temp = 5, temp = temp+1 = 6, count = 6
Thread B: temp = 5, temp = temp+1 = 6, count = 6
```

Final result: `count = 6`, but it should have been `7` since two increments happened. One update got "lost" because of bad timing.

**How to fix it (minimize race conditions):**
1. **Locks/Mutex** – only one process can enter the shared section at a time.
2. **Semaphores** – a signaling method to control access.
3. **Atomic operations** – hardware ensures an operation completes fully, without interruption.

**Fix using a lock (code):**
```c
lock.acquire();
count = count + 1;   // safe now, no other thread can jump in
lock.release();
```

---

### 16. Busy Waiting

Busy waiting = a process **keeps checking again and again** in a loop if it can proceed, instead of resting.

```c
while (lock == 1) {
    // keep checking... wastes CPU time
}
```

**Problem:** CPU is stuck doing nothing useful the whole time.

---

### 🔑 Diff: Busy Waiting vs No Busy Waiting

| Busy Waiting | No Busy Waiting |
|---|---|
| Keeps checking again and again | Goes to sleep, wakes up only when ready |
| Wastes CPU time | Frees CPU for other work |
| Example: `while(lock==1){}` | Example: semaphore with sleep/wakeup |

**Easy way to remember:** Busy waiting = repeatedly knocking on a door. No busy waiting = ringing the doorbell and walking away until someone answers.

---

### 17. Critical Section

A **critical section** is the part of code where a process uses **shared data** — and only **one process should be allowed inside it at a time**.

**3 Rules a good solution must follow:**
1. **Mutual Exclusion** – only one process inside at a time.
2. **Progress** – if no one's inside, someone waiting must be allowed in (no infinite blocking).
3. **Bounded Waiting** – a process shouldn't wait forever; there's a limit on how many times others go first.

**Basic structure (code):**
```c
acquire_lock();     // entry
// critical section (shared data used here)
release_lock();     // exit
```

---

### 🔑 Diff: Process vs Program

| Program | Process |
|---|---|
| A file stored on disk (like `.exe`) | A program that is currently running |
| Doesn't use CPU/memory by itself | Uses CPU and memory while running |
| Passive — just sits there | Active — doing something right now |
| Stays the same until edited | Keeps changing state (running/waiting etc.) |

**Easy way to remember:** A *recipe* in a cookbook = Program. Someone actually *cooking* using that recipe = Process.

---

## Quick Revision Table

| Term | One-line meaning |
|---|---|
| OS | Software managing hardware for the user |
| System Call | How a program asks OS for help |
| Process | A running program |
| PCB | ID card the OS keeps for a process |
| Context Switch | CPU switching from one process to another |
| Starvation | A process never getting its turn |
| Aging | Raising priority over time to fix starvation |
| Multiprogramming | Many programs in memory to keep CPU busy |
| Multitasking | Fast switching to feel like everything runs together |
| IPC | Processes talking/sharing data |
| Race Condition | Wrong result due to bad timing on shared data |
| Busy Waiting | Repeatedly checking in a loop, wasting CPU |
| Critical Section | Code part needing exclusive access to shared data |

---

*Tip: for every definition question, write it as — (1) one-line meaning, (2) a real example. That covers full marks in most short-answer OS questions.*
