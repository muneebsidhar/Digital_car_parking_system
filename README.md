# 🚗 Digital Car Parking Gate System (7 Segment Display)

An automatic car parking gate system built entirely from standard **digital logic ICs**. Infrared sensors detect vehicles entering and leaving, and a 7 segment display shows the number of free parking slots in real time. When the parking area is full, the entry gate signal is blocked automatically.

No microcontroller and no programming are needed.

---

## 📖 Overview

Counting vehicles by hand is slow and causes mistakes and overcrowding. This project gives a simple, low-cost alternative for small parking areas such as buildings, offices, shopping centres and educational institutions.

- A vehicle **enters**: the available slot count goes **down by one**
- A vehicle **exits**: the available slot count goes **up by one**
- The parking area is **full**: the entry gate signal is blocked until a vehicle leaves

---

## 🎯 Objectives

- Detect vehicles entering and leaving using infrared sensors
- Update the available slot count on a 7 segment display immediately
- Block entry automatically when the parking area is full
- Build a simple, efficient and low-cost system from standard digital logic ICs

---

## ✨ Features

- Real-time display of available parking slots
- Separate IR sensors for the entry and exit gates
- Automatic full-condition detection that blocks the entry gate
- Entry is allowed again as soon as a vehicle exits
- No microcontroller or software required
- Tested in simulation (Proteus) and on a physical breadboard

---

## 🧰 Components Used

| Component | Purpose |
| --------- | ------- |
| IR sensors (2) | Detect vehicles at the entry and exit gates |
| 74LS192 | Up/Down counter that counts vehicles |
| 7447 | BCD to 7 segment decoder / display driver |
| 7 segment display | Shows the number of available slots |
| NOR gate | Detects the full condition (counter output 0000) |
| Breadboard and jumper wires | Circuit assembly |
| 5V DC power supply | Powers the circuit |

**Software:** Proteus Design Suite (simulation)

---

## ⚙️ How It Works

1. The IR sensors monitor the entry and exit points. A vehicle interrupts the infrared beam.
2. Each sensor sends a clock pulse to the 74LS192 counter, which changes the count by one.
3. The four BCD output lines of the counter (QA, QB, QC, QD) go to the inputs of the 7447 decoder (A, B, C, D).
4. The 7447 converts the BCD value into 7 segment signals, and the display shows the available slots.
5. A NOR gate is connected to all four BCD output lines. When the output is `0000` (no free slots), its output goes HIGH and disables the entry gate signal.
6. When a vehicle exits and a slot is freed, entry is allowed again automatically.

---

## 🖼️ Project Images

Add your screenshots and photos here, for example:

- Proteus simulation: empty parking
- Proteus simulation: full parking, entry blocked
- Physical breadboard circuit

```markdown
![Proteus - empty parking](images/proteus_empty.png)
![Proteus - full parking](images/proteus_full.png)
![Breadboard circuit](images/breadboard.jpg)
```

---

## 🛠️ Problems Faced and Solutions

| Problem | Cause | Solution |
| ------- | ----- | -------- |
| False vehicle detection by the IR sensor | Ambient light, wrong sensitivity, vibrations | Adjusted the sensitivity potentiometer and shielded the sensor from direct light |
| Wrong or garbled digits on the display | Incorrect wiring between the 74LS192 and 7447, loose breadboard connections | Re-checked every connection against the datasheets and secured loose jumper wires |
| Entry gate not blocking when full | Incorrectly wired full-condition logic | Redesigned it with a NOR gate on all four counter outputs and verified it in Proteus first |

---

## ⚠️ Limitations

- A single 7 segment display limits the system to a maximum of **9 slots**

---

## 🔮 Future Improvements

- Mount the circuit on a PCB or fixed board for a more stable layout
- Extend to a two-digit display by cascading a second 74LS192 counter and display (0 to 99 slots)
- Test under different light levels, vehicle sizes and speeds
- Fine-tune sensor sensitivity and reduce signal delays
- Add automatic barrier arms, LED indicators or wireless monitoring

---

## 👤 Author

**Muneeb Sidhar** (Muneeb Ur Rehman Sidhar)
Computer Science, University of Engineering and Technology (UET), Taxila

---

## 📜 License

This project is for educational purposes. You can add a license of your choice (for example, MIT) to this repository.
