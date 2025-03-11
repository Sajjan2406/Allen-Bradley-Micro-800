# **Virtual Commissioning: Sorting Boxes by Height**

## **Project Overview**
This project demonstrates the virtual commissioning of an automated sorting system using **Allen-Bradley Micro 800 PLC**, **Connected Components Workbench (CCW)**, and **Factory I/O**. The system sorts boxes based on height, directing small boxes to the left and large boxes to the right.

## **Technologies Used**
- **Connected Components Workbench (CCW):** PLC programming
- **Allen-Bradley Micro 800:** Virtual PLC for logic execution
- **Factory I/O:** 3D simulation of an industrial environment
- **Ladder Logic:** Programming language used for automation logic

## **System Components & Sensors**
### **Components:**
- **Virtual PLC:** Allen-Bradley Micro 800 (via CCW)
- **Simulation Environment:** Factory I/O
- **Conveyors:** Main, Left, and Right conveyors
- **Control Panel:** Start button, Start light

### **Sensors Used & Their Functions:**
| Sensor Name       | Function |
|-------------------|----------|
| **Pallet Sensor (BOOL_IN_2)** | Detects the presence of a box on the conveyor |
| **Loaded Conveyor Sensor (BOOL_IN_3)** | Detects when an object is loaded onto the conveyor |
| **At Left End Sensor (BOOL_IN_4)** | Detects when a box reaches the left conveyor end |
| **At Right End Sensor (BOOL_IN_6)** | Detects when a box reaches the right conveyor end |
| **At Left Exit Sensor (BOOL_IN_5)** | Ensures the box exits to the left |
| **At Right Exit Sensor (BOOL_IN_7)** | Ensures the box exits to the right |
| **Low Sensor (BOOL_IN_1)** | Detects small boxes |
| **High Sensor (BOOL_IN_0)** | Detects large boxes |
| **Very High Sensor (BOOL_IN_14)** | (Future Expansion) Detects extra-large boxes |

## **Sorting Logic**
1. **Box Detection:** The system detects a box on the conveyor.
2. **Height Measurement:**
   - If **Low Sensor = ON** and **High Sensor = OFF**, the box is **small** → Sent left.
   - If **High Sensor = ON**, the box is **large** → Sent right.
3. **Sorting Execution:**
   - **Small Boxes:** Transfer Left (`BOOL_OUT_3`), Move via Left Conveyor (`BOOL_OUT_5`)
   - **Large Boxes:** Transfer Right (`BOOL_OUT_4`), Move via Right Conveyor (`BOOL_OUT_6`)
4. **Exit Confirmation:** Sensors confirm successful box sorting.
5. **Control Panel Interaction:** Start button enables the process, and start light provides system feedback.

## **Setup Instructions**
### **1. Load the Factory I/O Scene**
- Open **Factory I/O** and load the provided scene file (`.factoryio`).

### **2. Load the PLC Program**
- Open **Connected Components Workbench (CCW)**.
- Import the provided PLC program (`.CCW` file).

### **3. Establish Communication**
- In **CCW**, set the **Micro 800 PLC IP Address**.
- Connect **Factory I/O** to the same IP.

### **4. Run the Simulation**
- Switch the PLC mode to **RUN**.
- Start the simulation in **Factory I/O**.
- Press the **green push button** om the **Control Panel** to begin sorting.

## Simulation
Watch the simulation in action on YouTube:  

[![Watch the Simulation](https://img.youtube.com/vi/u1eKG-m84Vk/0.jpg)](https://youtu.be/u1eKG-m84Vk)  
 
