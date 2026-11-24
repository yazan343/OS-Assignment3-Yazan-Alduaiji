# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Yazan Alduaiji |
| **Student ID** | 446050343 |
| **University Email** | 446050343@std.psau.edu.sa |
| **GitHub Username** | yazan343 |
| **Repository Link** | https://github.com/yazan343/OS-Assignment3-Yazan-Alduaiji |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---


## Your Development Log

### Entry 1 - November 25, 2026, 12:09 AM

**What I did**: Set up my GitHub repository and student ID.

**Details**:
- Forked and renamed the starter repository.
- Configured Git using my university email.
- Set my student ID to 446050343.
- Ran the original program and saved its output.
- Committed and pushed my changes.

**Challenges**: The original program produced incorrect results and thread errors.

**Solution**: Identified the shared resources that needed synchronization.

**Time spent**: Approximately 20 minutes (estimated).

---

### Entry 2 - November 25, 2026, 12:35 AM

**What I did**: Implemented Feature 1.

**Details**:
- Added a ReentrantLock called queueLock.
- Protected add(), poll(), processOf(), and snapshot().
- Used try/finally to release the lock safely.
- Ran five tests and pushed the changes.

**Challenges**: Multiple CPUs could access the same process in the ready queue.

**Solution**: Used a mutex lock to protect the shared list and map.

**Time spent**: Approximately 25 minutes.

---

### Entry 3 - November 25, 2026, 12:47 AM

**What I did**: Implemented Feature 2.

**Details**:
- Added a ReentrantLock called statsLock.
- Protected the three update methods and their getters.
- Used one lock for all three shared statistics.
- Ran five tests and pushed the changes.

**Challenges**: Some updates to the shared counters were lost.

**Solution**: Protected the shared statistics using mutual exclusion.

**Time spent**: Approximately 15 minutes.

---

### Entry 4 - November 25, 2026, 1:03 AM

**What I did**: Implemented Feature 3.

**Details**:
- Added a counting semaphore with an initial value of zero.
- Used release() when adding processes.
- Used acquire() before taking a process.
- Added a shutdown signal for waiting CPUs.
- Tested and pushed the changes.

**Challenges**: CPUs could remain blocked after all processes finished.

**Solution**: Released permits for all CPUs when all processes were completed.

**Time spent**: Approximately 15 minutes.

---

### Entry 5 - November 25, 2026, 1:14 AM

**What I did**: Completed the final correction and testing.

**Details**:
- Removed the remaining null polling branch.
- Reviewed the changes using git diff.
- Compiled the Java program successfully.
- Ran five consecutive tests.
- All four verification checks passed in every test.
- Committed and pushed the final correction.

**Challenges**: An editor change was not saved correctly.

**Solution**: Corrected the file and verified the changes before testing again.

**Time spent**: Approximately 10 minutes.

---

### Entry 6 - Optional

**What I did**: Not applicable.

**Details**: Five development entries are recorded above.

**Challenges**: Not applicable.

**Solution**: Not applicable.

**Time spent**: Not applicable.

---

## Development Log Summary

**Total time spent on assignment**: Approximately 1 hour and 25 minutes for setup, implementation, and testing, excluding documentation and video recording.

**Most challenging part**: Implementing the counting semaphore and ensuring that all CPUs terminate correctly.

**Most interesting learning**: Understanding how mutex locks prevent race conditions and how semaphores eliminate busy waiting.

**What I would do differently next time**: Start earlier, spread the work across multiple days, and document each development session immediately.

---


# Part B: Reflection (0.5 mark)

## Question 1: What did you learn about synchronization?

**Your Answer:**

I learned that synchronization is important when multiple threads access shared data. Without synchronization, race conditions can cause incorrect results. I learned how to use ReentrantLock to protect critical sections. I also learned why the finally block is important for releasing locks safely. Using a counting semaphore helped eliminate busy waiting. The final results showed how synchronization can improve program correctness.

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

The most challenging part was implementing the counting semaphore. I needed to make CPUs wait when the ready queue was empty. I also needed to understand when to use acquire() and release(). Another important challenge was making sure that all CPUs stopped after the last process finished. Without a shutdown signal, some CPUs could remain blocked forever. The final tests showed that all processes completed successfully.

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

I worked on one feature at a time instead of changing everything together. I compared the original output with the expected results. I tested the program after implementing each feature. I used git diff to review my code changes and received guidance when I encountered problems. I also saved the output of my tests for comparison. Finally, all four verification checks passed in five consecutive runs.

## Question 4: Where can synchronization concepts be applied in real-world applications?

**Your Answer:**

Synchronization can be used in banking applications to protect shared account balances. It can also prevent two customers from booking the same seat. Database systems use synchronization to manage concurrent access to shared data. Mutex locks can protect critical sections in these applications. Semaphores can control access to limited resources, such as database connections. These concepts help prevent incorrect results and improve system reliability.

### Optional: What would you like to learn more about?

Deadlock prevention and advanced thread synchronization.

### Optional: How confident do you feel about synchronization concepts now?

Intermediate. I understand mutex locks, race conditions, and counting semaphores, but I need more practice with deadlock prevention.

### Optional: Feedback on the assignment

The assignment provides a practical example of synchronization in operating systems and demonstrates the importance of testing concurrent programs.

---

# Part C: Technical Answers (0.5 mark)

## Question 1: Race Condition in Your Own Output

**Your Answer:**

In my original program, the expected context switch count was 13, but the observed count was 11. Only 8 out of 10 processes were completed, and the total service time was incorrect. A race condition can happen when two threads read and update the same shared variable at the same time. RaceWindow.pause() increases the chance of losing an update by adding a delay between reading and writing. On a real machine, thread scheduling can cause the same problem without this delay, making it difficult to reproduce.

Verification block of the **original starter**:

```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
Context switches (quanta executed) expected 13 observed 11 ✘ MISMATCH
Completed processes               expected 10 observed 8 ✘ MISMATCH
Total service time (ms)           expected 19434 observed 16072 ✘ MISMATCH
Busy-waiting polls (must be 0)     expected 0 observed 609 ✘ MISMATCH
✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.
```

Verification block of **my final version**:

```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
Context switches (quanta executed) expected 13 observed 13 ✔
Completed processes               expected 10 observed 10 ✔
Total service time (ms)           expected 19434 observed 19434 ✔
Busy-waiting polls (must be 0)     expected 0 observed 0 ✔
✔ All shared values are consistent.
```

**Explanation of the timeline:**

An example of a possible lost update:

1. A process thread running on CPU-1 reads contextSwitchCount = 5.
2. The first thread executes RaceWindow.pause().
3. A process thread running on CPU-2 also reads contextSwitchCount = 5 and pauses.
4. The first thread writes 6.
5. The second thread also writes 6.
6. The final value is 6 instead of 7, so one update is lost.

## Question 2: Critical Sections and Lock Granularity

**Your Answer:**

I used queueLock to protect the shared ready queue and statsLock to protect the three shared statistics. I used one lock for all statistics because it is easier to manage, although this prevents independent statistics updates from running in parallel. I used a separate lock for the ready queue to avoid unnecessary blocking between queue and statistics operations. Mutual exclusion is achieved using lock() before the critical section and unlock() inside the finally block. Releasing locks safely supports progress, but the default non-fair ReentrantLock does not guarantee bounded waiting, so starvation is theoretically possible.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| ReadyQueue.add() | queueLock | Protects queue and map insertion |
| ReadyQueue.poll() | queueLock | Prevents duplicate or lost processes |
| ReadyQueue.processOf() | queueLock | Protects shared map access |
| ReadyQueue.snapshot() | queueLock | Protects queue iteration |
| incrementContextSwitch() and its getter | statsLock | Prevents lost updates and unsafe reads |
| incrementCompletedProcess() and its getter | statsLock | Protects the completed process count |
| addServiceTime() and its getter | statsLock | Protects service time updates and reads |

## Question 3: Busy Waiting vs Semaphore

**Your Answer:**

The original program recorded 609 busy-waiting polls because CPUs repeatedly checked the empty ready queue after sleeping for 20 milliseconds. My counting semaphore starts at zero because the ready queue is initially empty. After adding the 10 initial processes, the semaphore has 10 permits representing available processes that CPUs can claim. When no permits are available, acquire() blocks the CPU thread instead of repeatedly checking the queue. At shutdown, release(SharedStats.totalCPUs) wakes the waiting CPUs so they can terminate instead of remaining blocked forever.

## Question 4: Classical Problems and Deadlock

**Your Answer:**

**Classical problem and roles**:

This simulation represents the producer-consumer problem, where the main thread produces the initial processes and CPU threads consume them. CPU threads also become producers when they return unfinished processes to the ready queue.

**Semaphores for a bounded queue (name and initial value)**:

A bounded queue with capacity K requires empty = K, full = 0, and mutex = 1.

**Deadlock scenario and prevention**:

If a producer holds the mutex while waiting for an empty slot in a full queue, the consumer cannot acquire the mutex to remove an item. Waiting for an available slot or item before acquiring the mutex prevents this scenario by breaking the circular-wait dependency.

## Summary

**Key concepts I understood through these questions:**

1. Race conditions and mutual exclusion.
2. Mutex locks and critical sections.
3. Counting semaphores and busy-waiting prevention.

**Concepts I need to study more:**

1. Deadlock prevention.
2. Bounded waiting and thread fairness.

---


# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
