## 📦 **3.4 Transmission Impairment**

Signals degrade as they travel through a transmission medium due to **three primary impairments**:

### **1. Attenuation (Loss of Energy)**

* Signal loses energy due to **resistance in the medium** (e.g., heat in wires).
* **Solution**: Use **amplifiers** to boost signal strength.

#### 📐 Measured using **Decibels (dB)**:

* Formula (based on power):

  $$
  \text{dB} = 10 \log_{10} \left(\frac{P_2}{P_1}\right)
  $$
* Negative dB = **Loss**; Positive dB = **Gain**
* Example:

  * Power halved → –3 dB
  * Power increased ×10 → +10 dB

#### dBm (decibels relative to 1 mW):

$$
\text{dBm} = 10 \log_{10}(P_\text{mW})
$$

---

### **2. Distortion (Signal Shape Change)**

* Happens when **composite signals** have components with **different propagation speeds**, causing **phase shifts**.
* Result: Received waveform is **distorted** (not same shape as sent).
* Most common in **high-speed or wideband channels**.

---

### **3. Noise (Unwanted Energy)**

Several types:

| **Noise Type** | **Description**                              |
| -------------- | -------------------------------------------- |
| **Thermal**    | Random motion of electrons                   |
| **Induced**    | From electrical devices (e.g., motors)       |
| **Crosstalk**  | Signal from one wire affects another         |
| **Impulse**    | Sudden spikes (e.g., lightning, power lines) |

---

### **Signal-to-Noise Ratio (SNR)**

* Measures **signal quality**:

  $$
  \text{SNR} = \frac{\text{Signal Power}}{\text{Noise Power}} \quad \text{(unitless)}
  $$

  $$
  \text{SNR}_{\text{dB}} = 10 \log_{10}(\text{SNR})
  $$
* Higher SNR = **better** quality.
* Ideal (but impossible) SNR = ∞ (no noise).

---

## ⚡ **3.5 Data Rate Limits**

Defines **how fast** data can be sent over a channel (in bits per second). Influenced by:

1. **Bandwidth (Hz)**
2. **Signal Levels (L)**
3. **Noise (SNR)**

---

### **1. Nyquist Bit Rate (Noiseless Channel)**

$$
\text{BitRate} = 2 \times \text{Bandwidth} \times \log_2 L
$$

* L = number of signal levels
* Bandwidth in Hz
* **Higher L → higher BitRate**, but harder to distinguish

#### Examples:

* 3000 Hz, 2 levels → 6000 bps
* 3000 Hz, 4 levels → 12,000 bps
* Want 265 kbps at 20 kHz? Need ≈ 99 levels (choose 64 or 128 practically)

---

### **2. Shannon Capacity (Noisy Channel)**

$$
\text{Capacity} = \text{Bandwidth} \times \log_2(1 + \text{SNR})
$$

* Gives **theoretical maximum** for noisy channels
* Independent of signal levels

#### Examples:

* Telephone line: 3000 Hz, SNR=3162 → ≈ 34.86 kbps
* 2 MHz, SNRdB = 36 → SNR = 3981 → ≈ 24 Mbps

---

### **Combining Both (Practical Use)**

* **Shannon**: defines **upper bound**
* **Nyquist**: shows **needed signal levels** to reach a desired bit rate

#### Example:

* Channel: 1 MHz, SNR = 63 → Shannon: 6 Mbps max
* Choose 4 Mbps → Nyquist → L = 4 levels

---

## 📊 **3.6 Performance Metrics**

---

### **1. Bandwidth**

| **Type** | **Definition**         |
| -------- | ---------------------- |
| **Hz**   | Range of frequencies   |
| **bps**  | Max data transfer rate |

* More bandwidth (Hz) → higher possible data rate (bps)

---

### **2. Throughput**

* **Actual** data transferred per second
* Always ≤ bandwidth
* Affected by:

  * Network congestion
  * Device limitations

#### Example:

* Bandwidth: 10 Mbps
* 12,000 frames/min × 10,000 bits → Throughput ≈ 2 Mbps

---

### **3. Latency (Delay)**

Time from message **start to complete arrival**. Made up of:

| Component        | Formula / Definition                               |
| ---------------- | -------------------------------------------------- |
| **Propagation**  | Distance / Propagation Speed                       |
| **Transmission** | Message Size / Bandwidth                           |
| **Queuing**      | Wait time in buffers (depends on traffic)          |
| **Processing**   | Time to examine/process header info at each device |

#### Examples:

* 2.5 KB message @ 1 Gbps, 12,000 km →

  * Propagation = 50 ms
  * Transmission = 0.02 ms

* 5 MB message @ 1 Mbps →

  * Propagation = 50 ms
  * Transmission = 40 s

---

### **4. Bandwidth-Delay Product**

* Represents **"volume" of the pipe** → number of bits "in flight"

$$
\text{Bandwidth} \times \text{Delay} = \text{Number of bits in the link}
$$

* Example:

  * Bandwidth = 1 bps, Delay = 5s → Link holds 5 bits
  * Bandwidth = 5 bps, Delay = 5s → Link holds 25 bits

---

### **5. Jitter**

* Variation in **packet delay**
* Affects **real-time** applications (e.g., VoIP, video calls)
* Low jitter = smooth playback; high jitter = choppy experience

---

## ✅ **Quick Reference Table**

| Concept               | Formula / Meaning                 |
| --------------------- | --------------------------------- |
| **dB (attenuation)**  | $10 \log_{10}(P_2 / P_1)$         |
| **Nyquist Bit Rate**  | $2 \times B \times \log_2 L$      |
| **Shannon Capacity**  | $B \times \log_2(1 + \text{SNR})$ |
| **Propagation Time**  | Distance / Speed                  |
| **Transmission Time** | Message Size / Bandwidth          |
| **Bandwidth (Hz)**    | Frequency range                   |
| **Bandwidth (bps)**   | Bit rate capacity                 |
| **Throughput**        | Actual transfer rate              |
| **Jitter**            | Delay variation                   |
| **Bandwidth × Delay** | Bits that can be “in-flight”      |

