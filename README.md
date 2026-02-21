# ✈️ Airport Queue Optimization

Discrete-event simulation of an airport security checkpoint to determine the optimal number of service stations while maintaining an average wait time under 1 minute.

---

## 📌 Problem

Airport security must balance two competing goals:

- Minimize operational cost (fewer service stations)
- Maintain high service quality (low wait times)

The objective of this project is to determine the minimum number of service stations (k) required to keep average traveler wait time below 1 minute under stochastic arrivals and service times.

---

## ⚙️ Approach

### 1️⃣ Base Model (M/G/k Approximation)

- Poisson arrivals (λ = 10/min)
- Stochastic service times (Uniform and Truncated Normal)
- Travelers join the shortest queue (greedy routing)
- FIFO service discipline

Implemented using an **object-oriented discrete-event simulation engine** built with:
- Priority queue scheduling (`heapq`)
- Event-driven time progression
- Time-weighted queue length tracking

---

### 2️⃣ Extended Model (Blocking + Bottleneck)

Introduced real-world complexity:

- 3% probability of secondary screening
- Shared senior officer (single bottleneck)
- Blocking effect: stations remain occupied during secondary inspection

This creates interdependent queues that cannot be solved analytically, requiring simulation.

---

## 📊 Analysis

- Theoretical M/G/1 validation (Pollaczek–Khinchine formula)
- Stability analysis via traffic intensity (ρ)
- Empirical simulation across k = 5–17
- 95% confidence intervals across 50 trials
- Comparison of:
  - Average wait time
  - Average queue length
  - Maximum queue length

---

## 🎥 Video Explanation

📽️ [Project Walkthrough – Simulation & Optimization Explained](https://drive.google.com/file/d/1xZEjj-EZorFcMt5mIno5-1NuRMejrQxo/view?usp=drive_link)

---

## ✅ Result

Optimal staffing level:

> **k = 10 service stations**

This configuration:
- Keeps average wait time below 1 minute
- Maintains system stability
- Prevents congestion spikes caused by secondary screening

---

## 🧠 Why This Project?

This project combines:

- Queueing theory
- Discrete-event simulation
- Stochastic modeling
- Systems optimization

It demonstrates how analytical models and simulation can be combined to inform real-world operational decisions.
