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
| **Full Name** | Joud Ibrahim Hazazi |
| **Student ID** | 445052049 |
| **University Email** | 445052049@std.psau.edu.sa |
| **GitHub Username** | JoudIbrahim8 |
| **Repository Link** | https://github.com/JoudIbrahim8/OS-Assignment3-Joud-Hazazi |
 
---

## 🎥 Video Link

**Video Link**: https://drive.google.com/file/d/1RXiAWCjMPOVpgsqbdh--RWvu4erlMkqr/view?usp=drivesdk

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

> **Date note**: I was told by my instructor that same-day dates are acceptable. The five entries below describe actual work phases from November 13, 2026; exact times were not tracked.

### Entry 1 - November 13, 2026, late morning (Pacific Time; approximate)
**What I did**: Forked and renamed the Assignment 3 repository, set my student ID, and ran the original starter.

**Details**:
- Created my public fork and named it `OS-Assignment3-Joud-Hazazi`.
- Set my student ID in `SchedulerSimulationSync.java` and committed that setup change.
- Ran the original starter and copied its output into this file for comparison.

**Challenges**: At first I was unsure which repository copy to use and where to edit the Java file.

**Solution**: I checked that my repository was forked from the official starter, then opened its `SchedulerSimulationSync.java` file.

**Time spent**: Part of an approximately one-hour total; individual phase times were not tracked.

---

### Entry 2 - November 13, 2026, late morning (Pacific Time; approximate)
**What I did**: Used an AI coding assistant to add the mutex lock protecting the ready queue.

**Details**:
- The assistant added `queueLock` to `ReadyQueue` with my direction.
- The assistant protected `add()`, `poll()`, `processOf()`, and `snapshot()` with `lock()` and `try/finally`.
- Kept `RaceWindow` unchanged and inside the protected `poll()` operation.

**Challenges**: In the starter run, CPU-1 and CPU-2 both picked P1, and the same thread was started twice.

**Solution**: Made the read/remove operation in `poll()` mutually exclusive so only one CPU can take the queue head at a time.

**Time spent**: Part of an approximately one-hour total; individual phase times were not tracked.

---

### Entry 3 - November 13, 2026, late morning (Pacific Time; approximate)
**What I did**: Used an AI coding assistant to add a lock for the shared statistics.

**Details**:
- The assistant added one `statsLock` for the three shared statistics and their getters.
- The assistant used `try/finally` for every lock release.
- Chose one statistics lock to keep the synchronization logic straightforward, accepting that independent counter updates are serialized.

**Challenges**: The original run reported 28 context switches instead of 30 and 15 completed processes instead of 16.

**Solution**: Protected each statistics update and read so concurrent CPUs cannot overwrite or read an in-progress update.

**Time spent**: Part of an approximately one-hour total; individual phase times were not tracked.

---

### Entry 4 - November 13, 2026, late morning (Pacific Time; approximate)
**What I did**: Used an AI coding assistant to replace busy waiting with a counting semaphore and add CPU shutdown signaling.

**Details**:
- The assistant initialized `readyCount` to 0 and released one permit whenever a process was added.
- The assistant changed each CPU to acquire a permit before taking a process.
- The assistant added a shutdown release for CPUs waiting after the final process completes.

**Challenges**: The starter recorded 1,034 busy-wait polls, and CPUs could otherwise remain blocked at shutdown.

**Solution**: Used the semaphore to block until work is available and released permits for all CPUs when work is complete.

**Time spent**: Part of an approximately one-hour total; individual phase times were not tracked.

---

### Entry 5 - November 13, 2026, late morning (Pacific Time; approximate)
**What I did**: Ran the completed version and worked with an AI coding assistant to document, commit, and push the changes.

**Details**:
- The final Java source was compiled and run five times: one IDE run by me and four additional local runs with assistant help.
- Each run showed 30 context switches, 16 completed processes, 87649 ms total service time, and 0 busy-wait polls.
- Recorded the actual starter and final outputs in this file.
- Used an AI coding assistant for implementation and documentation help; I need to be able to explain the changes in my video.

**Challenges**: VS Code showed a Java Language Server restart error during one step, and the assignment log asked for dates the instructor allowed to be the same day.

**Solution**: Reloaded VS Code and confirmed the program output, then recorded the five real work phases with the same date as permitted by my instructor.

**Time spent**: Part of an approximately one-hour total; individual phase times were not tracked.

---

### Entry 6 - Optional
No additional work phase to record.

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: Approximately 1 hour so far (estimate; not timed).

**Most challenging part**: Understanding how the unprotected queue could make two CPUs select the same thread and lose a different process.

**Most interesting learning**: A semaphore can represent available queue items and block CPUs without busy waiting.

**What I would do differently next time**: Keep a work log from the first session and make each feature commit as soon as that feature is complete.

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

The starter showed me how a race condition can happen when two CPUs use shared data at the same time. In my original run, CPU-1 and CPU-2 both picked P1, and Java reported `IllegalThreadStateException` because the same thread was started twice. A `ReentrantLock` makes only one CPU at a time read and remove from `ReadyQueue`. I also saw that shared counters need protection, including their getters, because an increment involves a read and a write. The lock must be released in a `finally` block so an exception does not leave other CPUs waiting. The semaphore starts at zero and blocks CPUs until a process is available, which removes repeated empty-queue polling. In the final runs, all four verification values matched their expected values.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The hardest part was understanding that the program could continue after CPU-1 threw an exception while still losing a process. Both CPUs selected P1, and later P2 had a zero-time row; the starter reported that only 15 of 16 processes completed. The queue race was hard to spot because `poll()` read the first element, paused in `RaceWindow.pause()`, and then removed the first element afterward. I needed to separate that issue from lost updates in the statistics and the busy-wait loop. Protecting the queue, statistics, and waiting logic in different ways clarified what each feature solved. Comparing the original expected and observed totals with the final output made the result easier to check.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I first ran the unmodified starter and kept its output, which showed duplicate P1 selection, a watchdog, and mismatched totals. Then I examined `ReadyQueue.poll()` and the `RaceWindow.pause()` between reading and removing the queue head. The queue methods are protected by `queueLock`, and the statistics methods and getters use `statsLock`. The queue semaphore is initialized to zero; each add releases a permit, and a CPU acquires one before polling. When the last process completes, the worker releases permits so CPUs blocked in `acquire()` can exit. I ran the final program five times and checked that all four values matched in each run.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

An online ticketing site can have several requests trying to reserve the same seat. A lock can protect the seat record so only one request changes it at a time. A semaphore can count available workers or tickets so requests wait instead of repeatedly checking. A print server has a shared queue where several jobs and workers interact, and locking keeps queue updates safe. These examples use the same ideas as this program: protect shared data and block when no work or resource is available.

### Optional: What would you like to learn more about?

I would like to learn more about deadlock prevention and how real operating systems schedule multiple CPUs.

### Optional: How confident do you feel about synchronization concepts now?

Beginner. I can identify the queue race and explain what the lock and semaphore do, but I need more practice tracing concurrent code independently.

### Optional: Feedback on the assignment

The starter output made the queue race visible. A short example showing the order of operations in `poll()` helped me connect the exception to the missing lock.

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

In my original run, CPU-1 and CPU-2 both picked P1, and CPU-1 then reported `IllegalThreadStateException` at `CpuWorker.run`. The two CPUs can also lose a statistics update if each reads the same counter value, pauses at `RaceWindow.pause()`, and writes back the same incremented value. On a real computer, the operating system can interrupt a thread between a read and write even without the artificial pause, so the failure may be rare and hard to reproduce. My starter run ended with a watchdog and the mismatched verification values shown below.

Verification block of the **original starter**:
```
⛔ WATCHDOG: the simulation did not finish (41 s).
Context switches (quanta executed) expected 30 observed 28 ✘ MISMATCH
Completed processes                    expected 16 observed 15 ✘ MISMATCH
Total service time (ms)                expected 87649 observed 81021 ✘ MISMATCH
Busy-waiting polls (must be 0)         expected 0 observed 1034 ✘ MISMATCH
```

Verification block of **my final version**:
```
Context switches (quanta executed) expected 30 observed 30 ✔
Completed processes                    expected 16 observed 16 ✔
Total service time (ms)                expected 87649 observed 87649 ✔
Busy-waiting polls (must be 0)         expected 0 observed 0 ✔
✔ All shared values are consistent.
```

**Explanation of the timeline:**
For a lost counter update, CPU-1 reads the current `contextSwitchCount` value n. CPU-2 reads the same n before CPU-1 writes, and both pass through `RaceWindow.pause()`. CPU-1 writes n+1, then CPU-2 also writes n+1, so two quanta were counted as one. The actual starter output showed 28 context switches when 30 were expected.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

`ReadyQueue.add()`, `poll()`, `processOf()`, and `snapshot()` use `queueLock` to protect the shared list and map. `SharedStats` uses one `statsLock` for all three counters and their getters; this is simple, but it serializes independent statistics updates. The queue has its own lock so queue operations do not need to hold the statistics lock. These locks provide mutual exclusion and allow a waiting thread to make progress when the lock is released, but the default non-fair `ReentrantLock` does not guarantee bounded waiting or rule out starvation.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()`, `poll()`, `processOf()`, `snapshot()` (`list` and `map`) | `queueLock` | Prevent duplicate or lost removals and protect map access and snapshot iteration. |
| `SharedStats` updates and getters (`contextSwitchCount`, `completedProcessCount`, `totalServiceTime`) | `statsLock` | Prevent lost read-modify-write updates and protect concurrent reads. |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

The starter repeatedly checked an empty queue and slept for 20 ms; my run recorded 1,034 busy-wait polls. The semaphore represents the number of processes available in the ready queue: it starts at 0, and after the 16 initial `add()` calls it has 16 permits. Each `add()` releases a permit, and each CPU acquires one before taking a process. After the last process finishes, a CPU releases `totalCPUs` permits so waiting CPUs can wake and exit; without that signal, they could remain blocked and the watchdog would fire.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

This is the producer-consumer (bounded-buffer) problem: `main` initially produces ready-queue entries, CPUs consume them, and a CPU also produces an entry when it re-enqueues an unfinished process. For a bounded queue of capacity K, the semaphores are `empty = K`, `full = 0`, and `mutex = 1`. If a producer held `mutex` while waiting for an empty slot, a consumer could not acquire the mutex to remove an item and create a slot, so both would wait. Acquiring `empty` before `mutex` avoids holding the mutex while waiting and breaks the hold-and-wait condition.

**Classical problem and roles**:
`main` is the initial producer; CPU workers consume queue items and also produce when re-enqueuing unfinished processes.

**Semaphores for a bounded queue (name and initial value)**:
`empty = K`, `full = 0`, `mutex = 1`.

**Deadlock scenario and prevention**:
If a producer holds `mutex` while waiting for an empty slot, a consumer cannot acquire `mutex` to remove an item. Acquire `empty` before `mutex` to break hold-and-wait.

## Summary

**Key concepts I understood through these questions:**
1. A race condition can corrupt a shared queue or lose a counter update when threads interleave.
2. `ReentrantLock` protects critical sections, and `try/finally` ensures the lock is released.
3. A counting semaphore lets CPUs block until a ready process is available and supports clean shutdown.

**Concepts I need to study more:**
1. How non-fair locks affect bounded waiting and starvation.
2. How to choose lock granularity and prevent deadlock in a bounded producer-consumer queue.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [x] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [x] Repository is renamed to `OS-Assignment3-Joud-Hazazi`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [x] Student ID is set in `SchedulerSimulationSync.java`
- [x] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [x] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [x] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [x] **The four verification lines are ✔ in 5 consecutive runs**
- [x] Every lock is released in a `finally` block
- [x] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [x] Each feature has clear comments

**Commits**
- [x] **At least 4 meaningful commits, ideally 7 or more**
- [x] **One commit per feature**
- [x] Commit dates are all November 13, 2026, as permitted by the instructor (per Joud).
- [x] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [x] Full name and student ID filled in at the top
- [x] Development log has five real work-phase entries dated November 13, 2026, as permitted by the instructor (per Joud).
- [x] Reflection: 4 questions, 5-7 sentences each
- [x] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [x] No `[...]` placeholders left
- [x] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Public video link is added to the **Video Link** section after Joud records the video


**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
