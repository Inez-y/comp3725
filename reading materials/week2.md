## 📘 **Chapter 3: Data and Signals**

---

### **3.1 Data and Signals**

#### **Overview**

In physical layer communication, actual **signals** are transmitted over a medium—not data directly. Data must be converted into signals (analog or digital) before transmission.

#### **Five Levels of Communication (Figure 3.1)**

1. **Application**
2. **Transport**
3. **Network**
4. **Data-link**
5. **Physical** (actual signal transmission)

Only the physical layer involves *physical transmission*; the rest are *logical*.

---

### **3.1.1 Analog and Digital Data**

| Term             | Description                                                               |
| ---------------- | ------------------------------------------------------------------------- |
| **Analog Data**  | Continuous values (e.g., voice, temperature, analog clock)                |
| **Digital Data** | Discrete values (e.g., text, integers, digital clock showing 8:05 → 8:06) |

* **Analog data** can be converted to analog or digital signals.
* **Digital data** can be transmitted as:

  * Digital signals (preferred in computers and LANs)
  * Modulated into analog signals (for legacy or long-distance transmission)

---

### **3.1.2 Analog and Digital Signals**

| Signal Type        | Characteristics                                                           |
| ------------------ | ------------------------------------------------------------------------- |
| **Analog Signal**  | Infinite number of levels over time (smooth transitions; e.g., sine wave) |
| **Digital Signal** | Finite number of levels (commonly 0 or 1; step-like transitions)          |

* Signals are often plotted as:

  * **Vertical axis**: Amplitude
  * **Horizontal axis**: Time
    *(See Figure 3.2 for visual comparison)*

---

### **3.1.3 Periodic and Nonperiodic Signals**

| Type                   | Description                                                         |
| ---------------------- | ------------------------------------------------------------------- |
| **Periodic Signal**    | Repeats a pattern over time (e.g., sine wave with period T)         |
| **Nonperiodic Signal** | No repeating pattern (e.g., burst of data in digital communication) |

* **Analog Signals**: Often periodic (e.g., AC power)
* **Digital Signals**: Typically nonperiodic (e.g., binary transmission)

> ⚠️ In data communication:
>
> * **Use periodic analog signals**
> * **Use nonperiodic digital signals**

---

## 🌀 **3.2 Periodic Analog Signals**

---

### **3.2.1 Sine Wave: The Basic Periodic Signal**

A **simple sine wave** is the building block of all analog signals and is defined by:

1. **Peak Amplitude (A)**

   * Maximum value from 0 (measured in volts)
   * Proportional to signal strength
   * Example: Home power \~155V peak, though advertised as 110–120V (rms value)

2. **Frequency (f)** and **Period (T)**

   * **Period (T)**: Time for one full cycle (in seconds)
   * **Frequency (f)**: Cycles per second = `1 / T` (in Hertz)
   * Common units:

     * 1 Hz = 1 cycle/s
     * 1 kHz = 1,000 Hz
     * 1 MHz = 1,000,000 Hz
   * Example: 60 Hz → T = 1/60 = 16.6 ms

3. **Phase (φ)**

   * Position of waveform at time zero (t = 0)
   * Measured in **degrees** (°) or **radians (rad)**

     * 0° = starts at 0 crossing upward
     * 90° = peak amplitude
     * 180° = inverted start
   * Example: 60° = `π/3` radians

---

### **3.2.2 Frequency as a Measure of Change**

* High frequency = rapid signal change
* Low frequency = slow signal change
* **Extreme cases**:

  * Constant signal → 0 Hz (unchanging)
  * Instantaneous change → ∞ Hz (idealized concept)

---

### **3.2.3 Wavelength (λ)**

* **Wavelength**: Distance a signal travels in one period
* Formula:

  $$
  \lambda = \frac{c}{f}
  $$

  * `λ`: Wavelength (in meters or micrometers)
  * `c`: Propagation speed (e.g., \~3 × 10⁸ m/s in vacuum)
  * `f`: Frequency (in Hz)
* Common in **optical transmission** (e.g., red light \~0.75 μm wavelength)

---

### **3.2.4 Time vs Frequency Domains**

| **Time Domain**               | **Frequency Domain**                   |
| ----------------------------- | -------------------------------------- |
| Amplitude vs Time             | Amplitude vs Frequency                 |
| Shows shape of wave           | Shows signal components                |
| Useful for real-time tracking | Useful for analyzing composite signals |

* A **pure sine wave** = one spike in frequency domain
  *(Figure 3.8 and 3.9 show how multiple sine waves become multiple spikes)*

---

### **3.2.5 Composite Signals**

* **Composite Signal** = multiple sine waves added together
* Real-world analog data (e.g., voice, music) are **composite**
* Frequency domain helps identify the **component frequencies**
* Key to understanding **bandwidth** and **signal analysis** (covered in later chapters)

---

### ✅ **Quick Definitions**

| Term                 | Definition                                |
| -------------------- | ----------------------------------------- |
| **Amplitude**        | Strength of the signal (volts)            |
| **Frequency**        | Number of cycles per second (Hz)          |
| **Period**           | Time per cycle (s), T = 1/f               |
| **Phase**            | Shift of wave at time 0 (degrees/radians) |
| **Wavelength**       | Distance traveled in one cycle: λ = c/f   |
| **Time Domain**      | Signal over time                          |
| **Frequency Domain** | Signal components by frequency            |

---
