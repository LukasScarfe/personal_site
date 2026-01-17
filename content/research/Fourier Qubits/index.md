---
title: "High-dimensional quantum key distribution with Qubit-like states"
date: 2025-11-25
description: "Introducing Fourier-qubits (F-qubits) to simplify state preparation and measurement in high-dimensional QKD while maintaining increased information density."
summary: "We introduce a high-dimensional QKD protocol using qubit-like states that are superpositions of only two computational basis states. This simplifies experimental implementation while providing a measured sifted key rate above 1 bit per photon in a noisy 4-dimensional channel."
tags: ["Quantum Key Distribution", "Quantum Cryptography", "Fourier-qubits", "Qubit-like States", "Orbital Angular Momentum", "Phase Error Rate"]
categories: ["Research"]
showSummary: true
showAuthor: false
showDate: true
showReadingTime: false
showWordCount: false
math: true
---

{{< katex >}}

{{< dynamic-img 
    light="https://raw.githubusercontent.com/LukasScarfe/Google-Scholar/refs/heads/master/plots/light/Highdimensional_quantum_key_distribution_with.png"
    dark="https://raw.githubusercontent.com/LukasScarfe/Google-Scholar/refs/heads/master/plots/dark/Highdimensional_quantum_key_distribution_with.png"
    alt="Citation Count"
    caption=" [Source](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=_eBW18oAAAAJ&citation_for_view=_eBW18oAAAAJ:Y0pCki6q_DkC)" 
>}}

## [**Click here for the full manuscript published in Communications Physics**](https://www.nature.com/articles/s42005-025-02376-8)

While Quantum Key Distribution (QKD) is theoretically secure, moving from theory to the real world is difficult. My recent research focuses on bridging the gap between high-dimensional protocols—which can carry more information per photon—and the technical simplicity required for practical, commercial hardware. We achieve this by using "qubit-like" states in a high-dimensional space, which we call **Fourier-qubits (\(F\)-qubits)**.

## The Problem: The Complexity of High Dimensions
Most QKD systems today operate in two dimensions (using qubits), most often implements with the polarization of light. High-dimensional (HD) QKD is attractive because it allows us to send more than one bit of information per photon and provides better tolerance against noise and eavesdropping.

However, the "go-to" HD protocols require states that are superpositions of *all* possible values in a given dimension \(d\). As \(d\) increases, the experimental setup to measure these superposition states becomes exponentially more complex and prone to errors. This technical hurdle is the primary reason most commercial systems still stick to simple two-dimensional protocols.

## Our Solution: Fourier-Qubits
We introduced a protocol that uses the standard logical basis (the most simple form of basis) but replaces the secondary Fourier basis with **\(F\)-qubits**. 

An \(F\)-qubit is a superposition of only **two** logical states, regardless of how high the dimension of the system is. The information is stored in the relative phase between these two states, which can take \(d\) different values. 

{{< equation >}}
  \[ |\phi_{jk}^{m} \rangle = (|j\rangle + \omega_d^m|k\rangle)/\sqrt{2} \]
{{< /equation >}}

where \({\omega_d= e^{2 \mathrm{\pi i} /d }}\), \({j \in\{0,1...,d-2\}}\), \({k\in\{1,2,...,d-1\}}\), with \( j< k\), and \({m\in\{0,1,...,d-1\}}\).


{{< figure
    src="img/4DFQubits.png"
    alt="Fourier Qubits in OAM"
    caption="\(F\)-Qubits in the OAM basis"
    >}}

### Why this works:
* **Simpler Hardware:** Because we only ever interfere two states at a time, the measurement complexity remains constant even as the dimension grows.
* **High Efficiency:** In systems using Spatial Light Modulators (SLMs), \(F\)-qubits utilize more of the active area of the device than traditional high-dimensional states.
* **Security:** We mathematically proved that even though these states look "two-dimensional," they can still be used to bound the information leaked to an eavesdropper in a high-dimensional Hilbert space.

## Experimental Demonstration
To test the protocol, we built a lab-scale free-space link using the **Orbital Angular Momentum (OAM)** of light. We used a 4-dimensional Hilbert space where information is encoded in the "twist" of the light beam.


### The Setup:
* **Source:** A 633 nm laser and a Spatial Light Modulator (SLM) to shape the \(F\)-qubit modes.
* **The Channel:** We simulated real-world atmospheric conditions using a turbulent cell and used an adaptive optics system (a deformable mirror) to correct the wavefront in real-time. The details of why we would do this can be found in the video at the bottom, and also in the [Supplementary Material](https://static-content.springer.com/esm/art%3A10.1038%2Fs42005-025-02376-8/MediaObjects/42005_2025_2376_MOESM2_ESM.pdf).
* **The Result:** Even with added noise, we achieved a secret key rate of **1.28 bits per photon**. This shows that our system works to transmit high-dimensional information even in a noisy environment.


## Key Takeaways
Our work demonstrates that you can use less complex quantum states to reap the rewards of high-dimensional communication. 
1. **Efficiency:** We maintained the benefit of increased information density while using simpler states (significantly more of them though).
2. **Robustness:** The protocol remained secure and functional in a noisy, turbulent environment.
3. **Scalability:** By fixing the measurement complexity to two modes, we've created a path for high-dimensional QKD that has a lower complexity barrier when it comes to measurement and generation.

## Negatives
It needs to be stated that even though we feel that the implementation of the \(F\)-Qubits does allow for simpler meaurements to be used for HD QKD, more modes are needed. The number of different states that you need to measure increases rapidly with dimension in this basis. This is an important drawback to keep in mind if you are designing a real-world system. As always there are tradeoffs.

## Conclusion
The introduction of \(F\)-qubits offers a practical "middle ground" for quantum communications. It provides the high-speed performance of high-dimensional spaces without the traditional experimental headaches. We foresee this being particularly useful in bandwidth-limited channels, such as satellite-to-ground links or fiber networks where detector recovery times usually limit speed.

---


{{<youtubeLite id="cRAmVcGRbr0"  label="HTSN Seminar Presentation">}}
A seminar where I talk about this work along with many others from the SQO research group.