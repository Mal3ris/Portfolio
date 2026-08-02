---
title: "Multithreaded Maze Solver"

categories:
- Software Engineering

tags:
- C++
- Multithreading
- Algorithms
- Atomics
- Condition Variables

weight: 5

summary: "A multithreaded C++ maze solver using concurrent breadth-first search, atomic synchronization, and path reconstruction."

showDate: false
showReadingTime: false
showWordCount: false
showAuthor: false
showBreadcrumbs: true
featured: false
---

*Multithreaded C++ application using concurrent breadth-first search, atomics, and condition variables to efficiently solve mazes.*

---

# Overview

The Multithreaded Maze Solver explores how concurrent algorithms can accelerate pathfinding by allowing multiple worker threads to search a maze simultaneously. Rather than assigning independent mazes to each thread, every thread collaborates on solving the same maze, coordinating through shared state to detect when a valid solution has been found.

The project emphasizes synchronization, concurrent algorithm design, and efficient communication between threads while demonstrating how atomics and condition variables can be used to safely coordinate work across multiple CPU cores.

---

|---|---|
| **Status** | <div class="status-badge status-completed"> <span class="status-dot"></span> Completed </div> |
| **Team Size** | Solo |
| **Duration** | Nov 2025 |
| **Language** | C++ |
| **Version Control** | Perforce |
| **Platform** | Windows |

---

## Technical Highlights

Implemented a concurrent maze-solving algorithm that combines parallel breadth-first search with lightweight synchronization and deterministic path reconstruction.

▶ [Parallel Breadth-First Search](#parallel-breadth-first-search)

▶ [Thread Synchronization](#thread-synchronization)

▶ [Path Reconstruction](#path-reconstruction)

▶ [Challenges & Lessons](#challenges-lessons)

---

<a id="parallel-breadth-first-search"></a><h1 class="section-title">Parallel Breadth-First Search</h1>

### Highlights

- Parallel bidirectional breadth-first search
- Concurrent exploration from the start and goal
- Reduced search space through simultaneous traversal

Rather than solving the maze from a single starting point, the solver launches two worker threads simultaneously. One thread begins a breadth-first search from the maze entrance while the other begins from the exit. Both threads expand through the maze independently, exploring new cells in parallel.

By searching from both ends at the same time, the algorithm reduces the amount of the maze each thread must explore before a solution is found. As the search frontiers grow toward one another, they eventually intersect, allowing the solver to terminate the search and reconstruct the complete path.

---

<a id="thread-synchronization"></a><h1 class="section-title">Thread Synchronization</h1>

### Highlights

- Atomic cell ownership
- Condition variables
- Race-free communication

To safely coordinate concurrent searches, every thread atomically "paints" each maze cell it visits with its own identifier. This allows ownership of a cell to be established without requiring coarse-grained locks.

When a thread encounters a cell that has already been claimed by another thread, a valid connection between the searches has been discovered. The threads then signal a shared condition variable, allowing all workers to terminate without unnecessary computation while avoiding race conditions.

This lightweight synchronization strategy minimizes contention while ensuring thread-safe communication between workers.

---

<a id="path-reconstruction"></a><h1 class="section-title">Path Reconstruction</h1>

### Highlights

- Parent tracking
- Solution stitching
- Deterministic reconstruction

Each thread maintains a record of the cells it visited during its breadth-first search. Once two searches intersect, the recorded paths from both threads are reconstructed and stitched together at the meeting point to produce a complete solution from the maze's start to its destination.

Separating path reconstruction from the search itself simplified synchronization while ensuring the final solution remained deterministic regardless of which threads discovered the intersection.

---

<a id="challenges-lessons"></a><h1 class="section-title">Challenges & Lessons</h1>

This project provided practical experience designing concurrent algorithms beyond simply dividing work across multiple threads. The most significant challenge was balancing parallel performance with safe synchronization while avoiding unnecessary locking that could reduce scalability.

Using atomics for cell ownership and condition variables for thread coordination demonstrated how lightweight synchronization primitives can enable efficient communication without introducing excessive contention. The project also reinforced the importance of designing algorithms that naturally parallelize rather than simply executing sequential work on multiple threads.

Overall, the Multithreaded Maze Solver strengthened my understanding of concurrent programming, synchronization, and algorithm design while providing hands-on experience with writing efficient multithreaded C++ applications.