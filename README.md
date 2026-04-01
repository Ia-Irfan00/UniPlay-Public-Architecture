# UniPlay-Public-Architecture
A high-leverage, Rust-powered game execution engine designed for  UniPlay replaces bloated software,and some game launchers with a decoupled, multi-threaded architecture (Scout Thread) that handles system-level indexing, users will be looking at a 30-40MB RAM footprint while gaming. Built for efficiency, transparency, and architectural integrity.
# UniPlay: High-Leverage Systems Architecture
**Low-Latency Game Indexing & Execution Engine**

## 🏛️ Architectural Thesis
Modern digital distribution platforms ofen succumb to "software bloat," consuming 500MB–1GB of idle RAM for simple library management. **UniPlay** acts as a systemic rebuttal to this trend. Built on the principle of **Resource Sovereignty**, it provides a high-fidelity interface for asset management with a memory footprint of **<30-40MB** while gaming.

## 🛠️ Technical Stack & Implementation
The system is engineered using a decoupled, multi-threaded architecture to ensure UI fluidity regardless of system-level I/O operations.

* **Core Engine (Back-end):** Developed in **Rust**. Leveraging zero-cost abstractions and memory safety to interface with the Windows Registry and filesystem.
* **The "Scout Thread":** A dedicated background worker thread designed to handle the heavy lifting of recursive directory scanning and registry indexing. It communicates with the UI layer via **Asynchronous Message Passing**, preventing any blocking of the main thread.
* **Interface Layer (Front-end):** A **Tauri-based** implementation using a custom-themed, hardware-accelerated UI. By utilizing the native OS webview, we bypass the overhead associated with Chromium-based frameworks like Electron.
* **State Management:** Optimized to handle high-frequency data updates from the Scout Thread without causing layout thrashing or CPU spikes.

## ⚖️ Systems Philosophy
As a systems architect, I believe that software should be a **servant** to the hardware, not a parasitic consumer. 

1.  **Efficiency as Fairness:** Every megabyte of RAM saved is a megabyte returned to the user’s primary task (gaming/creation).
2.  **Logic-First Design:** The "Scout Thread" is built for precision, ensuring that indexing is both exhaustive and non-intrusive to the user's workflow.
3.  **Digital Sovereignty:** No telemetry, no forced updates, and no background service persistence. The system exists only when called.

## 🚀 Development Status
* **Milestone:** Stable MVP (Architecture Complete).
* **Current Focus:** Registry key optimization, Scout Thread latency reduction, and UI/UX refinement.
* **Vision:** Transitioning from a standalone launcher to a comprehensive "Fair Business" ecosystem for digital assets.

---
**Architect: Imaad Akhtar Irfan
Contact Information: LinkedIn: Imaad Akhtar Irfan 
Email: irfnimaad06@gmail.com
Built at Age 19 | *Focusing on Systems, Logic, and Intellectual Integrity.*
