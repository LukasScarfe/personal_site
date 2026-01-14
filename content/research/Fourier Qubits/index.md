---
title: "High-dimensional quantum key distribution with Qubit-like states"
date: 2025-11-25
summary: "The research paper titled \"High-dimensional quantum key distribution with qubit-like states\" introduces a novel protocol for high-dimensional quantum key distribution (HD-QKD) that utilizes a new class of states called Fourier-qubits, or F-qubits, to enhance the efficiency and noise tolerance of quantum communications. Traditional HD-QKD protocols often rely on mutually unbiased bases (MUBs), where the secondary basis consists of balanced superpositions of all possible states in the logical basis, which can be technically challenging to implement and detect with high efficiency in certain degrees of freedom like orbital angular momentum (OAM). In this study, the authors propose replacing the traditional Fourier basis with F-qubits, which are qubit-like states formed by superpositions of only two logical states at a time with specific phase relationships derived from the roots of unity. This approach moves away from the requirement of full mutual unbiasedness while still providing a rigorous bound on the information leaked to a potential eavesdropper, thereby maintaining the security of the quantum channel. The researchers experimentally validated their protocol using a four-dimensional system based on the OAM degree of freedom of light, subjecting the signal to a noisy environment simulated by a turbulent cell and utilizing adaptive optics for correction. A key advantage of the F-qubit basis is its superior detection efficiency; because these states have a larger spatial intensity distribution compared to traditional MUB states, they utilize more of the active area of spatial light modulators, leading to higher signal-to-noise ratios. Their experimental results demonstrate that the F-qubit protocol can achieve high secret-key rates, with a calculated sifted key rate of 1.28 bits per photon in a noisy channel, and show that the phase error rate remains manageable even under adverse conditions. Furthermore, the F-qubit basis is overcomplete, containing more states than the standard BB84 protocol, which provides a more robust framework for error detection and characterization in high-dimensional systems. The study concludes that this qubit-like state approach significantly simplifies the preparation and detection stages of HD-QKD without sacrificing the inherent benefits of high-dimensional encoding, such as increased information capacity and higher tolerance to channel noise. By demonstrating a practical and efficient alternative to MUBs, the paper provides a feasible pathway for scaling quantum communication networks using various degrees of freedom, including time-bins and OAM, which are essential for future global-scale quantum secure communications and the development of a quantum internet. This work highlights how tailored state preparation can overcome traditional hardware limitations, offering a versatile tool for enhancing the performance of quantum cryptographic systems in real-world, noisy environments."
showAuthor: false
showDate: true
showReadingTime: false
showWordCount: false
---

{{< katex >}}

{{< dynamic-img 
    light="https://raw.githubusercontent.com/LukasScarfe/Google-Scholar/refs/heads/master/plots/light/Highdimensional_quantum_key_distribution_with.png"
    dark="https://raw.githubusercontent.com/LukasScarfe/Google-Scholar/refs/heads/master/plots/dark/Highdimensional_quantum_key_distribution_with.png"
    alt="Citation Count"
    caption=" [Source](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=_eBW18oAAAAJ&citation_for_view=_eBW18oAAAAJ:Y0pCki6q_DkC)" 
>}}

## [**Click here for the full manuscript published in Communications Physics**](https://www.nature.com/articles/s42005-025-02376-8)

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