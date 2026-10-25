# dsa-driven-OS-simulator
A C++17-based operating system simulator that explores how different data structures affect the performance, memory usage, and behavior of core OS components.

# DSA-Driven OS Simulator

A C++17-based operating system simulator that explores how different data structures affect the performance, memory usage, and behavior of core OS components.

Instead of building a bootable operating system kernel, this project simulates essential OS operations in user space, keeping the focus on **Data Structures and Algorithms (DSA)**.

## Project Objective

The central question this project investigates is:

> How does the choice of data structure affect the implementation and performance of an operating system component when the workload remains the same?

Each component provides a common interface with multiple interchangeable implementations. We run identical workloads against these implementations, collect performance metrics, and compare the results.

## Components

| Component | Responsible Member | Implementations |
|---|---|---|
| Process Scheduler | Zoya | Min-heap, sorted linked list, AVL tree |
| Memory Allocator | Shravani | First-fit, best-fit, worst-fit free lists; buddy system; bitmap or segregated free lists |
| Page Replacement | Ishita | FIFO, LRU, Clock |
| Deadlock Detection | Harsh | Resource allocation graphs, adjacency lists/matrices, DFS cycle detection, Banker's algorithm |

*The implementation details and final scope may be adjusted based on the project deadline and course requirements.*

## Technology Stack

- **Language:** C++17
- **Build system:** CMake or Make
- **Version control:** Git and GitHub
- **Testing:** CTest and/or a lightweight C++ unit-testing framework
- **Benchmarking:** Custom workload generators and a shared benchmark harness
- **Results:** CSV files and graphs

## Planned Project Structure

```text
dsa-driven-os-simulator/
├── common/                  # Shared models and interfaces
├── scheduler/               # Process scheduling algorithms
├── allocator/               # Memory allocation strategies
├── paging/                  # Page replacement policies
├── deadlock/                # Deadlock detection algorithms
├── harness/                 # Benchmarking and metrics collection
├── cli/                     # Command-line interface and demo
├── tests/                   # Unit and integration tests
├── docs/                    # Documentation and project report
├── results/                 # Benchmark outputs and graphs
├── CMakeLists.txt           # Build configuration
├── .gitignore
└── README.md
```

## How It Works

1. Select an OS component and its data structure implementation.
2. Generate or load a workload.
3. Execute the workload using the selected implementation.
4. Record correctness and performance metrics.
5. Run the same workload against alternative implementations.
6. Compare the results using CSV data, graphs, and complexity analysis.

The goal is to keep each component's interface consistent so that implementations can be compared fairly.

## Evaluation Metrics

| Component | Metrics |
|---|---|
| Scheduler | Waiting time, turnaround time, response time, context switches, operation time |
| Memory allocator | External fragmentation, internal fragmentation, failed allocations, allocation/free time |
| Page replacement | Page faults, hit ratio, access time, memory overhead |
| Deadlock detection | Detection time, memory usage, correctness across graph sizes and densities |

Random workloads should use fixed seeds to make experiments reproducible.

## Getting Started

### Prerequisites

Install:

- A C++ compiler supporting C++17 (GCC, Clang, or MSVC)
- Git
- CMake, if using the CMake build system

### Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd dsa-driven-os-simulator
```

Replace the placeholder with the actual repository URL.

### Build with CMake

Once `CMakeLists.txt` and the source files are available:

```bash
cmake -S . -B build
cmake --build build
```

Run tests if CTest has been configured:

```bash
ctest --test-dir build --output-on-failure
```

**Note:** These commands become usable after the team adds the corresponding build configuration, source files, and tests.

## Team Responsibilities

- **Zoya:** Process scheduler, shared process model, integration leadership, and report compilation.
- **Shravani:** Memory allocator, repository setup, build infrastructure, unit-test setup, and code-review coordination.
- **Ishita:** Page replacement, benchmark harness, CSV metrics, and graphs.
- **Harsh:** Deadlock detection, CLI demo, scenario runner, and presentation.

## Team Workflow

1. Each member works on a separate feature branch.
2. Shared interfaces and CSV column names are agreed upon before integration.
3. Changes are submitted through pull requests.
4. At least one teammate reviews each pull request before merging.
5. `main` should remain in a working state.
6. Unit tests and benchmark workloads are run before integration.
7. All benchmark results should be reproducible using documented workloads and random seeds.

## Project Deliverables

- A working C++17 OS simulator with multiple implementations per component
- Unit and integration tests
- Reproducible benchmark workloads
- CSV benchmark results and comparison graphs
- A report containing complexity analysis and experimental findings
- A command-line demonstration and presentation

## Scope

This is an **educational user-space simulator**, not a bootable operating system or a replacement for a real kernel. The emphasis is on DSA, algorithmic complexity, correctness, and evidence-based performance comparisons.

## Contributors

Zoya · Shravani · Ishita · Harsh
