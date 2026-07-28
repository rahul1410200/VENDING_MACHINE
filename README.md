# Vending Machine Controller Using Verilog FSM

## 📖 Introduction

This repository presents a **Finite State Machine (FSM)** based implementation of a **Vending Machine Controller** using **Verilog HDL**. The controller accepts three different coin denominations—**5¢ (Nickel), 10¢ (Dime), and 25¢ (Quarter)**. When the accumulated amount reaches or exceeds **50¢**, the machine dispenses an item. If the inserted amount is greater than the item cost, the remaining balance is returned as change.

---

## ✨ Main Features

- Accepts three coin denominations:
  - Nickel (5¢)
  - Dime (10¢)
  - Quarter (25¢)
- Product price fixed at **50¢**
- FSM keeps track of the accumulated credit
- Automatically dispenses an item once sufficient credit is received
- Returns excess amount as change
- Supports asynchronous reset to restore the initial state

---

## ⚙️ System Specifications

### Inputs

| Signal | Description |
|---------|-------------|
| `clk` | System clock |
| `reset` | Resets the controller to the initial state |
| `nickel` | Represents insertion of a 5¢ coin |
| `dime` | Represents insertion of a 10¢ coin |
| `quarter` | Represents insertion of a 25¢ coin |

### Outputs

| Signal | Description |
|---------|-------------|
| `item` | Indicates that the product has been dispensed |
| `change` | Displays the remaining balance returned to the user |

---

## 🔧 Design Parameters

| Parameter | Value |
|-----------|-------|
| Nickel Value | 5¢ |
| Dime Value | 10¢ |
| Quarter Value | 25¢ |
| Item Cost | 50¢ |

---

## 🏛️ FSM States

The controller uses multiple states to represent the accumulated credit.

| State | Credit |
|-------|--------|
| `s0` | 0¢ |
| `s1` | 5¢ |
| `s2` | 10¢ |
| `s3` | 15¢ |
| `s4` | 20¢ |
| `s5` | 25¢ |
| `s6` | 30¢ |
| `s7` | 35¢ |
| `s8` | 40¢ |
| `s9` | 45¢ |
| `s10` | 50¢ |
| `s11` | 55¢ |
| `s12` | 60¢ |
| `s13` | 65¢ |
| `s14` | 70¢ |
| `dispense_state` | Returns the machine to idle after dispensing |

---

## 🔄 Operating Principle

1. The controller begins from the idle state (**0¢**).
2. Each inserted coin updates the current credit.
3. Once the accumulated amount reaches **50¢ or more**, the vending machine dispenses the product.
4. If the total exceeds the product cost, the extra amount is returned as change.
5. After completing the transaction, the FSM returns to the idle state, ready for the next customer.

---

## 🧪 Sample Test Cases

| Coins Inserted | Result |
|---------------|--------|
| 25¢ + 25¢ | Product dispensed, no change |
| 25¢ + 25¢ + 5¢ | Product dispensed with 5¢ change |
| 10¢ + 10¢ + 25¢ | Total = 45¢, waiting for another coin |
| Reset asserted | FSM immediately returns to idle state |

---

## 📁 Repository Structure

```
project/
│── vending_machine.v      # FSM implementation
│── vending_machine_tb.v   # Simulation testbench
│── README.md              # Project documentation
```

---

## ▶️ Running the Design

1. Open the project in any Verilog simulator (Vivado, ModelSim, Xilinx ISE, etc.).
2. Compile both the design and the testbench.
3. Start the simulation.
4. Observe the **item** and **change** outputs using the waveform viewer or simulator console.

---

## 🚀 Possible Improvements

- Add support for additional coin denominations.
- Allow multiple product prices.
- Display the inserted balance using LEDs or seven-segment displays.
- Implement the design on an FPGA development board.

---

## 👨‍💻 Author

**Rahul Rathlavath**

Verilog HDL | Digital Design | Finite State Machine (FSM)
