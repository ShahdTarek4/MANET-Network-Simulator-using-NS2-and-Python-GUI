
# MANET Network Simulator using NS2 and Python GUI

This project provides a complete simulation and visualization platform for ***Mobile Ad Hoc Networks (MANETs)*** using ***NS2 (Network Simulator 2)*** and ***Python with Tkinter***. It provides side-by-side implementations of ***Proactive Routing (OLSR)*** and ***Reactive Routing (AODV)*** routing protocols, along with a Python-based GUI to visualize node movement and routing behavior, enabling users to explore the behavior, performance, and tradeoffs of both strategies. The simulation is intended for learning, analysis, and experimentation in wireless ad hoc networking environments. Furthermore, performance analysis scripts are also included for key metrics like ***throughput, packet delivery ratio (PDR), delay, packet loss, and overhead***.

  


## Table of Contents
1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Installation](#installation)
4. [Run NS2 Simulation](#run-ns2-simulation)
5. [Run Python GUI for Proactive Routing](#run-python-gui-for-proactive-routing)
6. [Run Python GUI for Reactive Routing](#run-python-gui-for-reactive-routing)
7. [Analyze Performance Metrics](#analyze-performance-metrics)
8. [Usage](#usage)
9. [Routing Protocols](#routing-protocols)
10. [Performance Metrics](#performance-metrics)
11. [Performance Analysis](#performance-analysis)
12. [References](#references)

---

## Project Overview

This simulator consists of:

1. **NS2 Simulation TCL Script:** Simulates the MANET environment and generates `.tr` and `.nam` files for analysis.
2. **Proactive Routing GUI (OLSR):** Interactive simulation of Proactive Routing Protocol behavior.
3. **Reactive Routing GUI (AODV):** Visual demonstration of Reactive Routing behavior with dynamic discovery.
4. **Performance Analysis Scripts:**
   - `graph.py`: Visualizes performance metrics.
   - `performance.awk`: Parses `.tr` files and computes metrics such as throughput, PDR, packet loss and overhead
   - `performance.txt`: Text file that Stores the computed results from the NS2 simulation.

---

## Features

### NS2 Simulation
- Dynamic node movement and real-time topology updates.
- Configurable simulation parameters (nodes, protocols, source/destination pairs).
- Generates `.tr`(trace) and `.nam`(animation) files for performance analysis and visualizing.

### Python GUI: Proactive (OLSR)
- Continuous routing table updates.
- Real-time node and route visualization.
- View routing tables and packet paths during transmission.

### Python GUI: Reactive (AODV)
- On-demand route discovery.
- RREQ and RREP visualization.
- Real-time node mobility and packet path display.

### Performance Analysis
- `performance.awk`: Calculates throughput, PDR, delay, etc., from trace file.
- `graph.py`: Visualizes metrics from `performance.txt`.

---

## Installation

### Requirements
- **Ubuntu/Mint (Any linux-based OS)**
- **NS2** with `nam_1.14_amd64`
- **Python 3.x**
- **Tkinter**
- **Matplotlib**

### Setup

1. **Clone Repository:**
```bash
git clone https://github.com/ShahdTarek4/MANET-Network-Simulator-using-NS2-and-Python-GUI.git
cd MANET-Network-Simulator-using-NS2-and-Python-GUI.git
```

2. **Install NS2 & NAM:**
```bash
sudo dpkg --install nam_1.14_amd64.deb

```

3. **Install Dependencies:**
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install build-essential autoconf automake gcc g++ perl libx11-dev xgraph xg xorg-dev libxt-dev libxmu-dev -y
```

4. **Download and Extract NS2**
```bash
cd ~
wget https://downloads.sourceforge.net/project/nsnam/allinone/ns-allinone-2.35/ns-allinone-2.35.tar.gz
tar -xvzf ns-allinone-2.35.tar.gz
cd ns-allinone-2.35
```

5. **Install Python Dependencies**
```bash
sudo apt-get install python3-tk
pip install matplotlib
```

---




## Run NS2 Simulation
Use the following command to run the simulation
```bash
ns sim.tcl <Number of Nodes> <Routing Protocol> <Source1> <Dest1> <Source2> <Dest2>
```

## NS2 Simulation Output 

<img width="635" alt="ns2_manets" src="https://github.com/user-attachments/assets/f4e83f59-9a51-42f8-87d8-57f1a86a30d4" />


## Run Python GUI for Proactive Routing
Use the following command to run the proactive routing GUI
```bash
python proactive_routing.py
```
## Proactive Routing GUI Output

<img width="638" alt="proactive_routing" src="https://github.com/user-attachments/assets/da6bf2b5-c305-4f5e-9030-d068d10fc1e8" />


## Run Python GUI for Reactive Routing
Use the following command to run the reactive routing GUI
```bash
python reactive_protocol.py
```
## Reactive Routing GUI Output
---
<img width="642" alt="reactive_routing" src="https://github.com/user-attachments/assets/f115d2dc-f84c-4ab1-ba4b-a62ae91b79a4" />


## Analyze Performance Metrics

1. Run the AWK script:
```bash
awk -f performance.awk AODV_10.tr
```

2. Visualize the metrics:
```bash
python graph.py
```
 Performance Metrics Visualization
 
<img width="635" alt="manets_metrics" src="https://github.com/user-attachments/assets/3b558462-e1e8-4f20-8223-fd412c3ce062" />


## Usage

### NS2 Simulation
- Runs the simulation and generates `.tr` and `.nam` files.
- View `.nam` file using `nam`.

### GUI Steps
1. Launch the GUI.
2. Start/Stop node movement.
3. Select source/destination.
4. Send packets and view results.
5. Visualize routing tables (Proactive only).

### Analysis
- Run AWK script after NS2 simulation.
- Visualize results using `graph.py`.

---

## Routing Protocols

### Proactive (OLSR)
- Constant route updates.
- Low latency.
- Higher overhead.

### Reactive (AODV)
- Route discovery on demand.
- Less overhead.
- Initial delay due to discovery process.

---

## Performance Metrics

- **Throughput:** Successful data rate.
- **PDR:** Packet Delivery Ratio.
- **Delay:** Average time for delivery.
- **Packet Loss:** Unsuccessful delivery rate.
- **Overhead:** Routing control overhead.

---

## Performance Analysis

- Run `performance.awk` on `.tr` file.
- Results saved in `performance.txt`.
- Visualized using `graph.py`.

---

## References

1. [NS2 Documentation](http://www.isi.edu/nsnam/ns/)
2. [Tkinter Docs](https://docs.python.org/3/library/tkinter.html)
3. [Matplotlib Docs](https://matplotlib.org/stable/contents.html)
4. GitHub Repository for SDN-MANET Reactive Firewall Simulators
5. GitHub Repository for NS2 MANET Simulations

---

*Developed for simulation and academic research of MANET protocol behavior.*
