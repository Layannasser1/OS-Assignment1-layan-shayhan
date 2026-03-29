# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[A process is an independent program in execution with its own memory space and system resources, while a thread is a smaller unit of execution within a process that shares the same memory and resources. Processes are considered heavyweight because they require more time and resources for creation and management, whereas threads are lightweight and faster to create and switch between.
In this assignment, threads were used instead of processes because they are more efficient for simulations. Threads share the same memory space, which makes communication faster and reduces overhead. This is especially important when handling multiple processes, as it improves performance and allows smoother scheduling behavior]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```▶ P1 executing quantum [4000ms] 
  ⚡ Quantum progress: [███████████████] 100%
  ⏸ P1 completed quantum 4000ms │ Overall progress: [████████████████░░░░] 81%
     Remaining time: 926ms
  ↻ P1 yields CPU for context switch

  ➕ P1 added to ready queue │ Burst time: 4926ms | Priority: 5
┌─ Ready Queue ─────────────────────────────────────────────────────────────────
│ [P3 → P4 → P5 → P6 → P7 → P8 → P9 → P10 → P11 → P1]
[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:In this example, process P1 did not finish execution because it still had 926ms remaining. After completing its time quantum, it was preempted and placed at the end of the ready queue. This allows other processes to run before P1 gets another turn. Eventually, P1 resumes execution and finishes. This behavior ensures fairness among all processes**
[Explain what's happening in the output snippet you pasted]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: [Process P1 is in the New state when it is first created before being added to the ready queue.]

2. **Runnable**: [P1 enters the Runnable state once it is added to the ready queue and is ready to execute but waiting for CPU allocation]

3. **Running**: [P1 is in the Running state when it is actively executing on the CPU]

4. **Waiting**: [After its time quantum expires and it has not finished, P1 is preempted and returned to the ready queue. At this point, it is no longer running but is in the Runnable (ready) state, waiting for its next turn]

5. **Terminated**: [P1 reaches the Terminated state after completing its execution]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Operating System Task Scheduling]

**Description**: 
[Modern operating systems such as Windows and Linux run multiple programs simultaneously, including user applications and background services]

**Why Round-Robin works well here**: 
[Round-Robin scheduling ensures that each program receives a fair share of CPU time. This improves system responsiveness and prevents any single process from monopolizing the CPU. As a result, users experience smoother multitasking and better system performance]

### Example 2: [Web Server Handling Requests]

**Description**: 
[Web servers handle multiple client requests at the same time, especially in high-traffic environments.]

**Why Round-Robin works well here**: 
[Using Round-Robin with threads allows the system to distribute CPU time evenly among all requests. This ensures fairness and prevents starvation, while also maintaining good response times for users. It is particularly effective in handling concurrent workloads]

---

## Summary

**Key concepts I understood through these questions:**
1. The importance of CPU scheduling fairness in system performance
2. The difference between processes and threads in terms of resource usage and performance
3. How Round-Robin scheduling manages the ready queue and ensures fairness

**Concepts I need to study more:**
1. Advanced thread synchronization techniques
2. Comparison between different CPU scheduling algorithms
