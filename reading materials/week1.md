# 1.1: Data Communications**:

### **1.1 What is Data Communication?**

* **Data communication** refers to the exchange of data between two devices via a transmission medium (e.g., wire, cable, radio).
* Requires both **hardware** and **software**.
* Four key characteristics:

  1. **Delivery** – Correct destination.
  2. **Accuracy** – No alteration or errors.
  3. **Timeliness** – Arrives on time (real-time for audio/video).
  4. **Jitter** – Consistency in packet arrival time (especially for video/audio).

---

### **1.1.1 Components of a Data Communication System**

1. **Message** – The actual data (text, audio, video, etc.).
2. **Sender** – Device that sends the message (e.g., computer, camera).
3. **Receiver** – Device that receives the message (e.g., monitor, TV).
4. **Transmission Medium** – Path the message travels on (e.g., wire, fiber, radio).
5. **Protocol** – Set of rules governing communication (ensures compatibility).

---

### **1.1.2 Data Representation**

* Data comes in different **forms** and each is represented using **bit patterns**:

  | Type        | Representation                                                                   |
  | ----------- | -------------------------------------------------------------------------------- |
  | **Text**    | Bit patterns using codes (e.g., Unicode, ASCII).                                 |
  | **Numbers** | Directly converted to binary for calculations.                                   |
  | **Images**  | Matrix of pixels, each with a bit pattern (e.g., black & white, grayscale, RGB). |
  | **Audio**   | Continuous signals (e.g., voice, music), represented electronically.             |
  | **Video**   | Sequence of images or continuous motion, like TV broadcast.                      |

---

### **1.1.3 Data Flow Modes**

Three modes define how data travels between devices:

| Mode            | Description                                          |
| --------------- | ---------------------------------------------------- |
| **Simplex**     | One-way only. Example: keyboard to monitor.          |
| **Half-Duplex** | Two-way, but one at a time. Example: walkie-talkies. |
| **Full-Duplex** | Two-way simultaneously. Example: phone calls.        |

* **Full-duplex** uses either separate channels or shared bandwidth for both directions.

# 1.2: Networks**:

---

### **1.2 What is a Network?**

* A **network** is a group of connected devices (hosts like computers or phones, and connecting devices like routers, switches, and modems) that communicate using wired or wireless media.

---

### **1.2.1 Network Criteria**

Three key characteristics define an effective network:

1. **Performance**

   * Measured by **transit time** (from sender to receiver) and **response time** (reply delay).
   * Depends on number of users, media type, hardware, and software.
   * Key metrics: **Throughput** (data volume) and **Delay** (time taken).

2. **Reliability**

   * Involves failure frequency, recovery time, and resilience in disasters.

3. **Security**

   * Ensures data is protected from unauthorized access, damage, and includes recovery procedures.

---

### **1.2.2 Physical Structures**

#### **Types of Connections**

* **Point-to-Point**: One device directly connects to another (e.g., remote to TV).
* **Multipoint**: Multiple devices share one link (simultaneous = spatial, turn-taking = temporal).

#### **Physical Topologies**

The physical arrangement of devices and links in a network:

| Topology | Description                                             | Advantages                                     | Disadvantages                                             |
| -------- | ------------------------------------------------------- | ---------------------------------------------- | --------------------------------------------------------- |
| **Mesh** | Every device connects to every other (n(n−1)/2 links).  | High fault tolerance, privacy, robustness.     | Expensive, complex cabling, requires many ports.          |
| **Star** | Devices connect to a central hub.                       | Easy to install/manage, fault isolation.       | Entire network fails if hub fails.                        |
| **Bus**  | One backbone cable with all devices connected via taps. | Easy, uses less cable.                         | Hard to troubleshoot, failure affects whole network.      |
| **Ring** | Each device connects to two others in a circle.         | Simple to add/remove devices, fault detection. | A break can disable the network unless dual ring is used. |




--- 
# 2.1: Protocol Layering**:


### **2.1 What is Protocol Layering?**

* A **protocol** defines rules for communication between devices.
* When communication tasks are complex, **protocol layering** is used to divide the task into smaller layers—each layer has its **own protocol**.

---

### **2.1.1 Scenarios for Understanding Layering**

#### **First Scenario: Simple One-Layer Protocol**

* Two friends (Maria and Ann) talk **face-to-face**.
* Only **one layer** is needed (talk/listen).
* Even here, communication follows rules (e.g., take turns, stay on topic).

#### **Second Scenario: Three-Layer Protocol**

* Ann moves away; they use **encrypted postal letters**.

* Tasks split across **three layers**:

  1. **Layer 3**: Talk/Listen → generate plaintext.
  2. **Layer 2**: Encrypt/Decrypt → convert to/from ciphertext.
  3. **Layer 1**: Send/Receive mail.

* Each layer uses its **own logic and machines**, allowing flexibility:

  * If encryption changes, only **Layer 2** needs to be updated.
  * This illustrates **modularity**.

---

### **Advantages of Protocol Layering**

* **Modularity**: Layers are independent, easier to maintain or replace.
* **Separation of services and implementation**: Layers provide services without needing to know how others work.
* **Intermediate systems** (e.g., routers) only use some layers, reducing complexity.

#### **Disadvantage**

* A single-layer approach might seem simpler, but is harder to scale and maintain.

---

### **2.1.2 Principles of Protocol Layering**

1. **Bidirectional Communication**

   * Each layer must support two opposing functions (e.g., send/receive, encrypt/decrypt).

2. **Identical Layer Objects**

   * At each layer on both ends, the exchanged objects must be of the same type (e.g., plaintext ↔ plaintext, ciphertext ↔ ciphertext).

---

### **2.1.3 Logical Connections**

* Layers can be visualized as having **logical connections** (peer-to-peer communication):

  * Each layer "talks" to its counterpart on the other device, even though the actual message passes through lower layers.
  * Helps conceptualize **how protocols operate across systems**.

# 2.2: TCP/IP Protocol Suite**:

### **2.2 TCP/IP Protocol Suite Overview**

* **TCP/IP** is a **suite of protocols** used in the Internet.
* It follows a **hierarchical, layered architecture**, originally with 4 layers, now commonly represented as **5 layers**:

  | Layer | Role        |
  | ----- | ----------- |
  | 5     | Application |
  | 4     | Transport   |
  | 3     | Network     |
  | 2     | Data Link   |
  | 1     | Physical    |

---

### **2.2.1 Layered Architecture in Action**

* In a network with hosts, routers, and switches:

  * **Hosts** use all 5 layers.
  * **Routers** use only Layers 1–3.
  * **Switches** use only Layers 1–2.

* **End-to-End Layers**: Application, Transport, Network.

* **Hop-to-Hop Layers**: Data Link, Physical.

---

### **2.2.2 Logical Connections & Identical Objects**

* **Logical communication** occurs between corresponding layers of the two hosts.
* Each layer works with **data units**:

  | Layer       | Data Unit             | Addresses Used          |
  | ----------- | --------------------- | ----------------------- |
  | Application | Message               | Site names (e.g., URLs) |
  | Transport   | Segment/User Datagram | Port numbers            |
  | Network     | Datagram              | IP addresses (global)   |
  | Data Link   | Frame                 | MAC addresses (local)   |
  | Physical    | Bits                  | None                    |

---

### **2.2.3 Duties of Each TCP/IP Layer**

| **Layer**       | **Duties**                                                                             |
| --------------- | -------------------------------------------------------------------------------------- |
| **Physical**    | Transmits raw bits over a medium (e.g., electrical, optical signals).                  |
| **Data Link**   | Moves frames across links; handles framing, addressing, and some error detection.      |
| **Network**     | Delivers packets (datagrams) host-to-host; handles IP addressing and routing.          |
| **Transport**   | Provides end-to-end delivery; uses protocols like TCP (reliable) and UDP (unreliable). |
| **Application** | Enables communication between software processes (e.g., HTTP, SMTP, FTP).              |

---

### **2.2.4 Encapsulation & Decapsulation**

* **Encapsulation** (at source): Each layer adds its **own header** (and sometimes trailer).

  * Message → Segment → Datagram → Frame → Bits
* **Decapsulation** (at destination): Each layer **removes its header** and passes the payload up.
* **Routers**: decapsulate at data link, inspect network-layer info, then re-encapsulate.

---

### **2.2.5 Addressing**

Each layer (except the physical layer) uses addresses for communication:

* **Application**: Host/domain names (e.g., `www.example.com`)
* **Transport**: Port numbers (e.g., 80 for HTTP)
* **Network**: IP addresses (e.g., `192.168.0.1`)
* **Data Link**: MAC addresses (e.g., `00:1A:2B:3C:4D:5E`)

---

### **2.2.6 Multiplexing & Demultiplexing**

* **Multiplexing**: A lower-layer protocol serves multiple upper-layer protocols.
* **Demultiplexing**: The reverse—decides which upper-layer protocol should receive the data.
* Protocol headers contain **fields** to identify the encapsulated protocol (e.g., TCP header identifies port number).

# 2.3: The OSI Model**:

---

### **2.3 What is the OSI Model?**

* **OSI** stands for **Open Systems Interconnection**.
* Developed by **ISO (International Organization for Standardization)** in the late 1970s.
* The **goal**: Create a universal standard for network communication—**interoperability** across different systems, regardless of architecture.

> **Note**: OSI is a *model*, not a protocol.

---

### **2.3.1 The OSI 7-Layer Model**

| **Layer**           | **Function**                                                               |
| ------------------- | -------------------------------------------------------------------------- |
| **7. Application**  | Interfaces directly with user applications (e.g., browsers, email).        |
| **6. Presentation** | Translates, encrypts, and compresses data (e.g., character encoding, SSL). |
| **5. Session**      | Manages sessions and dialog control (e.g., opening/closing connections).   |
| **4. Transport**    | Ensures reliable or unreliable data delivery (e.g., TCP, UDP).             |
| **3. Network**      | Handles logical addressing and routing (e.g., IP).                         |
| **2. Data Link**    | Manages framing and physical addressing (e.g., MAC).                       |
| **1. Physical**     | Transmits raw bits over a medium (e.g., cables, signals).                  |

---

### **OSI vs TCP/IP**

* **TCP/IP** combines the top 3 OSI layers (Application, Presentation, Session) into a single **Application layer**.
* **Transport, Network, Data Link, and Physical** layers align closely between both models.

| OSI Layer          | TCP/IP Equivalent    |
| ------------------ | -------------------- |
| 7–5 (App/Pres/Ses) | Application          |
| 4                  | Transport (TCP, UDP) |
| 3                  | Network (IP)         |
| 2                  | Data Link            |
| 1                  | Physical             |

---

### **2.3.2 Why OSI Did Not Replace TCP/IP**

1. **TCP/IP was already widely adopted** by the time OSI was finalized—replacing it would be costly.
2. **OSI's session and presentation layers were underdeveloped**—they lacked real protocols.
3. **OSI implementations underperformed** compared to the mature and practical TCP/IP suite.
