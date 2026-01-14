---
title: "High-dimensional quantum key distribution with Qubit-like states"
date: 2025-11-25
summary: "We introduced 'Fourier-qubits,' a new class of high-dimensional quantum states that simplify the complexity of secure communication while maintaining high data rates and noise resistance."
showAuthor: false
showDate: true
showReadingTime: false
showWordCount: false
---

{{< katex >}}

## [**Click here for the full manuscript published in Communications Physics**](https://doi.org/10.1038/s42005-025-02376-8)

While Quantum Key Distribution (QKD) is theoretically secure, moving from theory to the real world is difficult. My recent research focuses on bridging the gap between high-dimensional protocols—which can carry more information per photon—and the technical simplicity required for practical, commercial hardware. We achieve this by using "qubit-like" states in a high-dimensional space, which we call **Fourier-qubits (F-qubits)**.

## The Problem: The Complexity of High Dimensions
Most QKD systems today operate in two dimensions (using qubits), like the polarization of light. High-dimensional (HD) QKD is attractive because it allows us to send more than one bit of information per photon and provides better tolerance against noise and eavesdropping.

However, the "go-to" high-dimensional protocols require states that are superpositions of *all* possible values in a given dimension $d$. As $d$ increases, the experimental setup becomes exponentially more complex and prone to errors. This technical hurdle is the primary reason most commercial systems still stick to simple two-dimensional protocols.

## Our Solution: Fourier-Qubits
We introduced a protocol that uses the standard logical basis (the computational basis) but replaces the complex Fourier basis with **F-qubits**. 

An F-qubit is a superposition of only **two** logical states, regardless of how high the dimension of the system is. The information is stored in the relative phase between these two states, which can take $d$ different values. 


### Why this works:
* **Simpler Hardware:** Because we only ever interfere two states at a time, the measurement complexity remains constant even as the dimension grows.
* **High Efficiency:** In systems using Spatial Light Modulators (SLMs), F-qubits utilize the active area of the device much more efficiently than traditional high-dimensional states.
* **Security:** We mathematically proved that even though these states look "two-dimensional," they can still be used to bound the information leaked to an eavesdropper in a high-dimensional Hilbert space.

## Experimental Demonstration
To test the protocol, we built a lab-scale free-space link using the **Orbital Angular Momentum (OAM)** of light. We used a 4-dimensional Hilbert space where information is encoded in the "twist" of the light beam.


### The Setup:
* **Source:** A 633 nm laser and a Spatial Light Modulator (SLM) to shape the F-qubit modes.
* **The Channel:** We simulated real-world atmospheric conditions using a turbulent cell and used an adaptive optics system (a deformable mirror) to correct the wavefront in real-time.
* **The Result:** Even with added noise, we achieved a secret key rate of **1.28 bits per photon**. This is significantly higher than the theoretical limit of 1 bit per photon for standard two-dimensional systems.


## Key Takeaways
Our work demonstrates that you don't need infinitely complex quantum states to reap the rewards of high-dimensional communication. 
1. **Efficiency:** We maintained the benefit of increased information density ($\log_2(d)$ bits per photon).
2. **Robustness:** The protocol remained secure and functional in a noisy, turbulent environment.
3. **Scalability:** By fixing the measurement complexity to two modes, we've created a path for high-dimensional QKD that is actually feasible for next-generation telecommunications.

| Parameter | Measured Value |
| :--- | :--- |
| Dimension ($d$) | 4 |
| Bit Error Rate ($E_d$) | 2.89% |
| Phase Error Rate ($E_d'$) | 6.91% |
| **Final Key Rate** | **1.28 bits/photon** |

## Conclusion
The introduction of F-qubits offers a practical "middle ground" for quantum communications. It provides the high-speed performance of high-dimensional spaces without the traditional experimental headaches. We foresee this being particularly useful in bandwidth-limited channels, such as satellite-to-ground links or fiber networks where detector recovery times usually limit speed.

---