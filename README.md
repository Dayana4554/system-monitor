Desktop System Monitor
Overview

This Desktop System Monitor application is developed in C++ using the Dear ImGui library. It is designed to monitor various computer system resources and performance metrics, including CPU, RAM, SWAP, Fan, Network, and more. The use of Dear ImGui, an immediate mode GUI library, allows for an efficient and dynamic user interface.
Objectives

The main objective of this project is to demonstrate the acquired programming logic and the ability to adapt to new languages, specifically C++. This application is an extension of a given base code, with added features and enhancements to the existing Desktop System Monitor.
Features

- Real-time monitoring of system resources such as CPU, RAM, and SWAP.
- Performance metrics for Fan speed and Network usage.
- Dynamic and responsive GUI using Dear ImGui.
- Efficient data handling using the /proc filesystem in Linux.

Installation
Prerequisites

- Linux-based system
- C++ compiler (e.g., g++)
- SDL2 library: Install using apt install libsdl2-dev

Setting Up

1. Clone the repository:

```bash
git clone [URL_of_the_repository]
```

2. Navigate to the project directory:

```bash
cd system-monitor
```

3. Compile the project using the provided Makefile:

```bash
make
```

Usage

After successful installation, you can run the application by executing the compiled binary:

```bash
./system-monitor
```

The GUI will display various system metrics in real time. Navigate through different tabs to view CPU, RAM, SWAP, Fan, and Network statistics.
