# \# ⚡ Power Grid Designer

# 

# \*\*Course:\*\* ELE331 — Algorithms and Data Structure | \*\*Instructor:\*\* Dr. Abdelhamid Attaby  

# \*\*Institution:\*\* Benha University — Faculty of Engineering at Shoubra (Computer Engineering Division)

# 

# \---

# 

# \## 1. Project Concept

# \*\*Power Grid Designer\*\* is a Python-based electrical transmission network simulator and optimizer. It models generation plants and Substations as graph vertices, high-voltage transmission feeders as \*\*directed weighted edges\*\*, and local distribution lines as \*\*undirected weighted edges\*\*.

# 

# In strict compliance with ELE331 guidelines, all core data structures and algorithms are implemented \*\*100% from scratch\*\* without relying on built-in high-level collections (`dict`, `set`, `heapq`, `deque`, or `.sort()`).

# 

# \---

# 

# \## 2. Core System Capabilities

# Through an interactive CLI (Command Line Interface), the system delivers four engineering functions:

# 1\. \*\*Substation Lookup \& Ordered Reports:\*\* Instant station search by name ($O(1)$ avg via Hash Table), range/ordered queries via Binary Search Tree (Symbol Table), and sorted capacity/cost reports.

# 2\. \*\*Minimum-Cost Grid (MST):\*\* Selects the cheapest subset of cables to connect all substations without cycles using \*\*Prim's Algorithm\*\* and \*\*Kruskal's Algorithm\*\*.

# 3\. \*\*Cheapest Supply Path (Shortest Path):\*\* Computes the route with minimal energy dissipation (`power\_loss`) along directed/undirected feeders using \*\*Dijkstra's Algorithm\*\* and \*\*BFS\*\*.

# 4\. \*\*Fault Isolation (Connected Components):\*\* Dynamically removes damaged cables or stations and detects isolated regions experiencing blackouts via \*\*DFS \& BFS\*\*.

# 

# \---

# 

# \## 3. Dual-Weight Dataset Design (`data/`)

# Each cable in `cables.csv` carries two distinct weights to reflect real-world power engineering trade-offs:

# \* \*\*`install\_cost`:\*\* Upfront trenching and installation cost — optimized by \*\*Prim's \& Kruskal's Algorithms (MST)\*\*.

# \* \*\*`power\_loss`:\*\* Resistive energy loss during transmission — optimized by \*\*Dijkstra's Algorithm\*\*.

# 

# \---

# 

# \## 4. Architecture: Algorithms \& Custom Data Structures

# 

# | Feature / Module | Algorithm | Custom Data Structures (From Scratch) | Time Complexity |

# | :--- | :--- | :--- | :--- |

# | \*\*Station Lookup\*\* | Modular Hashing | `HashTable` (Separate Chaining) | $O(1)$ avg |

# | \*\*Ordered Queries\*\* | Tree Search \& Traversal | `BST` (Symbol Table) | $O(\\log N)$ avg |

# | \*\*Min-Cost Grid\*\* | Prim's \& Kruskal's (MST) | `Graph` + `MinHeap` + `UnionFind` | $O(E \\log V)$ |

# | \*\*Cheapest Supply Path\*\* | Dijkstra's \& BFS | `Graph` (Directed/Undirected) + `MinHeap` + `Queue` | $O(E \\log V)$ |

# | \*\*Fault Isolation\*\* | DFS \& BFS (Components) | `Graph` + `Stack` / `Queue` + Visited Array | $O(V + E)$ |

# | \*\*Grid Reporting\*\* | Mergesort \& Elementary Sorts | Primitive Arrays | $O(N \\log N)$ |

# | \*\*Performance Analysis\*\* | Doubling-Ratio Benchmarks | Synthetic Grids ($N = 500 \\dots 8000$) | Empirical |

# 

# \---

# 

# \## 5. Team Workload \& Development Milestones

# 

# | Member Name | Assigned Components | Target Milestone |

# | :--- | :--- | :--- |

# | \*\*Saif Ramadan\*\* | `Stack` \& `Queue`, `Graph` (Directed/Undirected), `Fault Isolation` (DFS/BFS), CLI Integration | M2 \& M3 |

# | \*\*Nada Refaat\*\* | `MinHeap` (Priority Queue), `UnionFind`, `MST` (Prim \& Kruskal), `Dijkstra's Shortest Path` | M2 \& M3 |

# | \*\*Hesham AbdElkhalek\*\* | `HashTable`, `BST` (Symbol Table), `Sorting` (Mergesort/Insertion), `Doubling-Ratio Benchmarks` | M2 \& Final |

# 

# \* \*\*M1 (Sun 29 Nov):\*\* Proposal finalized, repository published, components assigned.

# \* \*\*M2 (Sun 6 Dec):\*\* Core data structures (`Sorting`, `MinHeap`, `BST`, `HashTable`, `UnionFind`, `Stack/Queue`) completed and tested.

# \* \*\*M3 (Sun 13 Dec):\*\* Graph representations, `Fault Isolation`, `MST`, and `Dijkstra's Shortest Path` operational.

# \* \*\*Code Freeze (Sat 19 Dec):\*\* Empirical benchmarks, final documentation, and presentation slides completed.

# 

# \---

# 

# \## 6. Project Structure \& Execution

# 

# ```text

# Power-Grid-Designer/

# ├── data/               # substations.csv \& cables.csv

# ├── data\_structures/    # \_\_init\_\_.py, graph.py, hash\_table.py, bst.py, heap.py, queue\_stack.py, union\_find.py

# ├── algorithms/         # \_\_init\_\_.py, mst.py, shortest\_path.py, fault\_isolation.py, sorting.py

# ├── benchmarks.py       # Doubling-Ratio empirical timing tests

# └── main.py             # Interactive CLI entry point

