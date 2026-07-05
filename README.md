# OS Practice Exam — Full Marks: 30 | Pass: 15 | Your Target: 20+

| Section | Topic | Marks |
|---|---|---|
| Q1 | CPU Scheduling Numerical (SRTF) | 10 |
| Q2 | What is OS? | 2 |
| Q3 | Functions of OS | 3 |
| Q4 | Process vs Program | 3 |
| Q5 | PCB | 3 |
| Q6 | IPC | 3 |
| Q7 | Context Switching | 3 |
| Q8 | Busy Waiting vs No Busy Waiting | 3 |
| **Total** | | **30** |

---

# 📝 QUESTION PAPER

**Q1. (10 marks)** Consider the following processes with their Arrival Time (AT) and Burst Time (BT):

| Process | AT | BT |
|---------|----|----|
| P1 | 0 | 7 |
| P2 | 1 | 5 |
| P3 | 2 | 2 |
| P4 | 4 | 4 |
| P5 | 6 | 3 |

Using **Shortest Remaining Time First (SRTF)** scheduling:
(a) Draw the Gantt Chart (3 marks)
(b) Find CT, TAT, WT for each process (4 marks)
(c) Compute Average TAT and Average WT (3 marks)

**Q2. (2 marks)** What is an Operating System?

**Q3. (3 marks)** What are the functions of an Operating System?

**Q4. (3 marks)** Differentiate between a Process and a Program.

**Q5. (3 marks)** What is a PCB? What does it contain?

**Q6. (3 marks)** What is IPC? Why is it needed?

**Q7. (3 marks)** What is context switching?

**Q8. (3 marks)** What is the difference between Busy Waiting and No Busy Waiting?

---

# ✅ MODEL ANSWERS

## Q1. SRTF Numerical (10 marks)

### Gantt Chart
```
| P1 | P2 | P3 | P2 |  P5  |  P4  |     P1     |
0    1    2    4    6      8     11     15       21
```

### Table

| Process | AT | BT | CT | TAT | WT |
|---------|----|----|----|-----|-----|
| P1 | 0 | 7 | 21 | 21 | 14 |
| P2 | 1 | 5 | 8  | 7  | 2  |
| P3 | 2 | 2 | 4  | 2  | 0  |
| P4 | 4 | 4 | 15 | 11 | 7  |
| P5 | 6 | 3 | 11 | 5  | 2  |

### Averages
- **Average TAT** = (21+7+2+11+5) / 5 = **9.2**
- **Average WT** = (14+2+0+7+2) / 5 = **5**

---

## Q2. What is an Operating System? (2 marks)

An **Operating System (OS)** is software that sits between the **user** and the **computer hardware**.

It lets you use the computer without needing to know how the hardware works — it manages things like the CPU, memory, and files behind the scenes.

**Simple example:** Windows, Linux, and Android are all operating systems.

---

## Q3. Functions of OS (3 marks)

The OS does the following main jobs:

1. **Process Management** – starts, runs, and closes programs.
2. **Memory Management** – decides which program gets how much memory.
3. **File Management** – lets you create, open, save, and delete files.
4. **Device Management** – controls hardware like printers, keyboard, mouse.
5. **Security** – stops unauthorized users from accessing the system.

*(Just write these 5 points as a numbered list — simple and scores full marks.)*

---

## Q4. Process vs Program (3 marks)

| Program | Process |
|---|---|
| A file stored on disk (like a `.exe`) | A program that is currently running |
| Doesn't use CPU or memory by itself | Uses CPU, memory while it runs |
| Passive — just sits there | Active — doing something right now |
| Stays the same until you edit it | Keeps changing state (running, waiting, etc.) |

**Easy way to remember:** A *recipe* in a cookbook = Program. Someone actually *cooking* using that recipe = Process.

---

## Q5. PCB (3 marks)

**PCB = Process Control Block.**

It's like an **ID card** the OS keeps for every process, so it knows everything about that process.

**What it contains:**
- Process ID (a number to identify the process)
- Process state (running / waiting / ready)
- Program counter (which instruction is next)
- CPU registers (saved values)
- Memory info (how much memory it's using)
- I/O info (which devices it's using)

The OS uses this info whenever it needs to **pause** a process and **resume** it later.

---

## Q6. IPC (3 marks)

**IPC = Inter-Process Communication.**

It's simply **how different processes talk to each other and share data**.

**Why is it needed?**
1. Sometimes two processes need to **share the same information**.
2. Breaking a big task into smaller processes makes it **faster**, but they need to talk to combine results.
3. It makes the system **easier to manage** — smaller processes doing specific jobs instead of one giant one.

**Simple example:** When you copy text in one app and paste it in another, some form of communication is happening between them.

---

## Q7. Context Switching (3 marks)

**Context switching** is when the CPU **stops one process and starts another**.

Before switching, the OS **saves** everything about the current process (using its PCB) so it can be resumed exactly where it left off later.

**Why it matters:** This is what allows your computer to run many programs "at once" — even though the CPU is really just quickly switching between them.

**Downside:** Switching takes a small amount of time where **no actual work gets done** — this is called overhead. Too much switching slows the system down.

---

## Q8. Busy Waiting vs No Busy Waiting (3 marks)

| Busy Waiting | No Busy Waiting |
|---|---|
| The process keeps **checking again and again** if it can proceed | The process **goes to sleep** and is woken up only when ready |
| Wastes CPU time doing nothing useful | Frees up the CPU for other work while waiting |
| Example: `while(lock == 1) {}` | Example: using a semaphore that puts the process to sleep |

**Simple way to remember:** Busy waiting = repeatedly knocking on a door. No busy waiting = ringing a doorbell and walking away until someone answers.

---

# 🎯 Strategy to Score 20+/30

- **Q1 (Numerical) = 10 marks** — biggest single question. Practice this type until it's automatic.
- **Q4, Q5, Q8 (tables)** — easiest full marks, just memorize the table format.
- **Q2, Q3, Q6, Q7** — short definitions + simple example. Keep answers short and clear, don't overwrite.

**Target split:** Numerical 8/10 + Theory 16/20 = **24/30** — comfortably above your 20 goal.

**Tip:** Always write a short **example** in every theory answer — examiners give extra credit for that, and it's usually just one line.
