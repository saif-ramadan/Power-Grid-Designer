# ⚡ Power Grid Designer

# 

# Course: ELE331 — Algorithms and Data Structure | Instructor: Dr. Abdelhamid Attaby

# 

# Institution: Benha University — Faculty of Engineering at Shoubra (Computer Engineering Division)

# 

# 1\. Project Concept

# 

# Power Grid Designer is a Python-based electrical transmission network simulator and optimizer. It models power plants and Substations as graph vertices and transmission Cables as undirected weighted edges.

# 

# In compliance with ELE331 guidelines, all core data structures and algorithms are implemented 100% from scratch without relying on built-in high-level abstractions (dict, set, heapq, deque, or .sort()).

# 

# 2\. Core System Capabilities

# 

# Through an interactive CLI (Command Line Interface), the system delivers four engineering functions:

# 

# Substation Lookup \& Reports: Instant station search by name (O(1) average) and sorted capacity/cost reports.

# 

# Minimum-Cost Grid (MST): Selects the cheapest subset of cables to connect all substations without cycles.

# 

# Cheapest Supply Path (Shortest Path): Finds the route with minimal energy dissipation (power\_loss) from generation plants to target substations.

# 

# Fault Isolation (Connected Components): Dynamically removes damaged cables/stations and detects isolated regions experiencing blackouts.

# 

# 3\. Dual-Weight Dataset Design (data/)

# 

# Each cable in cables.csv carries two distinct weights to reflect real-world power engineering trade-offs:

# 

# install\_cost: Upfront trenching and installation cost — optimized by Prim's Algorithm (MST).

# 

# power\_loss: Resistive energy loss during transmission — optimized by Dijkstra's Algorithm.

# 

# 4\. Architecture: Algorithms \& Custom Data Structures

# 

# Feature / Module

# 

# Algorithm

# 

# Custom Data Structures (From Scratch)

# 

# Complexity

# 

# Station Lookup

# 

# Modular Hashing

# 

# HashTable (Separate Chaining)

# 

# $O(1)$ avg

# 

# Min-Cost Grid

# 

# Prim's Algorithm (MST)

# 

# Graph + MinHeap + Visited Array

# 

# $O(E \\log V)$

# 

# Cheapest Supply Path

# 

# Dijkstra's \& BFS

# 

# Graph + MinHeap + Stack / Queue

# 

# $O(E \\log V)$

# 

# Fault Isolation

# 

# DFS \& BFS (Components)

# 

# Graph + Stack / Queue + Visited Array

# 

# $O(V + E)$

# 

# Grid Reporting

# 

# Mergesort \& Insertion Sort

# 

# Primitive Arrays

# 

# $O(N \\log N)$

# 

# Performance Analysis

# 

# Doubling-Ratio Benchmarks

# 

# Synthetic Grids ($N = 500 \\dots 8000$)

# 

# Empirical

# 

# Design Note: Prim's Algorithm was chosen over Kruskal's to directly reuse our custom MinHeap (already required for Dijkstra) and prevent cycles via a lightweight visited array.

# 

# 5\. Project Structure \& Execution

# 

# Power-Grid-Designer/

# ├── data/               # substations.csv \& cables.csv

# ├── data\_structures/    # graph.py, hash\_table.py, heap.py, queue\_stack.py

# ├── algorithms/         # mst.py, shortest\_path.py, fault\_isolation.py, sorting.py

# ├── benchmarks.py       # Doubling-Ratio empirical timing tests

# └── main.py             # Interactive CLI entry point

# 

# 

# Quick Start:

# 

# git clone https://github.com/saif-ramadan/Power-Grid-Designer.git

# cd Power-Grid-Designer

# python main.py          # Launch interactive CLI

# python benchmarks.py    # Run Doubling-Ratio benchmarks



