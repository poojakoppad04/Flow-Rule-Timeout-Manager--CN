# Flow Rule Timeout Manager

## Overview

This project implements a Flow Rule Timeout Manager using Software Defined Networking (SDN). It demonstrates how flow rules are dynamically installed in a switch, monitored, and automatically removed after an idle timeout using a controller (Ryu framework).

---

## Objective

To implement and analyze timeout-based flow rule management in an SDN environment, focusing on:

* Flow rule lifecycle
* Idle timeout behavior
* Automatic removal of expired rules
* Traffic-driven rule reinstallation

---

## Features

* Installation of flow rules using SDN controller
* Idle timeout configuration for each flow entry
* Automatic deletion of inactive/expired rules
* Real-time observation of rule lifecycle
* Traffic-based rule creation and removal
* Regression testing of timeout behavior

---

## Technologies Used

* Python
* Ryu SDN Framework
* OpenFlow Protocol
* Mininet (for network simulation)
* Linux environment

---

## Project Structure

```
Flow-Rule-Timeout-Manager/
│
├── controller.py          # Main SDN controller (flow timeout logic)
├── test_script.sh         # Script to generate traffic (optional)
├── README.md              # Project documentation
└── screenshots/           # Output images (flow tables, topology)
```

---

## Working Principle

1. Switch sends packet-in request to controller
2. Controller installs flow rules with idle timeout
3. If no packets match the rule for a period → rule expires
4. Expired rules are automatically removed from switch
5. New traffic triggers new rule installation
6. Entire lifecycle is monitored and analyzed

---

## How to Run

### 1. Start Ryu Controller

```bash
ryu-manager controller.py
```

---

### 2. Start Mininet Topology

```bash
sudo mn --topo single,2 --controller remote
```

---

### 3. Generate Traffic

Inside Mininet CLI:

```bash
h1 ping h2
```

---

## Expected Output

* Flow rules installed in switch table
* Idle timeout countdown starts
* Rules automatically removed after inactivity
* New rules created on new traffic

---

## Learning Outcomes

* Understanding SDN architecture
* Flow rule management in OpenFlow
* Timeout-based rule lifecycle handling
* Controller-switch communication
* Practical implementation of network automation

---

## Author
Pooja Koppad
