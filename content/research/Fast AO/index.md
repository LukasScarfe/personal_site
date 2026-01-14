---
title: "Fast adaptive optics for high-dimensional quantum communications in turbulent channels"
date: 2025-02-24
summary: "Quantum Key Distribution (QKD) offers a provably secure method for information transmission, yet its implementation in free-space channels remains hampered by atmospheric turbulence, which introduces significant phase aberrations and signal loss. This research paper investigates the use of a fast, high-resolution adaptive optics (AO) system to mitigate these effects in high-dimensional QKD protocols using structured photons, specifically those carrying orbital angular momentum (OAM). Higher-dimensional protocols are advantageous because they increase information density and offer higher tolerance for error rates compared to standard two-dimensional polarization-based schemes. The experimental setup utilizes an AO system from ALPAO featuring a deformable mirror (DM) with 97 actuators and a Shack-Hartmann wavefront sensor (WFS) operating in a closed-loop configuration. To correct for turbulence, the researchers use a Gaussian reference beam co-propagating with the signal beam, allowing real-time wavefront measurements and corrections at speeds up to 200 Hz. Initial benchmarks demonstrated that activating the AO system increased the average coupling efficiency of a Gaussian mode from 36.6% to 87.1%. Using quantum process tomography, the authors showed that while turbulence effectively depolarizes the channel and creates massive crosstalk, the AO system recovers the encoded states, maintaining channel fidelity above 98% for dimensions up to five. Furthermore, the study measured the quantum dit error rate (QDER) for dimensions up to ten. Without AO, the QDER exceeded the security threshold for all dimensions greater than two, making secure communication impossible under the moderate turbulence conditions of $D/r_{0}=1.70$. However, with AO active, the QDER was reduced by an average of 32.5% across all tested cases, successfully bringing the error rate below the theoretical limit for positive secret key rates in almost all tested scenarios. The researchers noted that while OAM modes are highly sensitive to phase distortions, the AO system was more effective at reducing crosstalk in these logical bases than in the angular mode bases at higher dimensions due to the localized nature of those modes. These results demonstrate that advanced AO systems can enable secure free-space quantum communications in turbulent environments, such as ground-to-satellite or underwater links, where traditional methods fail."
showAuthor: false
showDate: true
showReadingTime: false
showWordCount: false
---

{{< katex >}}

{{< dynamic-img 
    light="https://raw.githubusercontent.com/LukasScarfe/Google-Scholar/refs/heads/master/plots/light/Fast_adaptive_optics_for_highdimensional.png"
    dark="https://raw.githubusercontent.com/LukasScarfe/Google-Scholar/refs/heads/master/plots/dark/Fast_adaptive_optics_for_highdimensional.png"
    alt="Citation Count"
    caption=" [Source](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=_eBW18oAAAAJ&citation_for_view=_eBW18oAAAAJ:IjCSPb-OGe4C)" 
>}}

## [**Click here for the full manuscript published in Communications Physics**](https://www.nature.com/articles/s42005-025-01986-6)

My colleagues and I at the University of Ottawa have been working to overcome atmospheric turbulence in free-space quantum communication for [a long time](https://opg.optica.org/optica/viewmedia.cfm?uri=optica-4-9-1006&html=true). This work focuses on using high-speed technology to "clean up" quantum signals so they can be sent securely over long distances in the atmosphere.

## Background: Free-Space Quantum Links
Quantum Key Distribution (QKD) provides a method for two parties to share secret keys with security guaranteed by the laws of physics. In essence this provides guaranteed secure communication, meaning literally nobody know what is being sent in the channel. While optical fibers are the backbone of our modern day internet, they suffer from significant signal loss over long distances when using quantum signals since they cannot be amplified without being destroyed. 

We strongly believe that to build a global quantum network (allowing globaly unhackable communications), we must use free-space links, like ground-to-satellite communications. However, the atmosphere is a very chaotic medium. Constant changes in temperature and pressure create turbulence that distorts the phase and structure of light. If you have ever seen the stars twinkling, you have seen this in action, as the twinkle is the effect of the dim starlight being deflected on around on its way to your eyes. We want to use the spatial shape of individual photons to pack more data into every signal, but the turbulence causes  different signals to overlap and become indistinguishable, resulting in high error rates.

{{<youtubeLite id="EZ7la-hMNuk"  label="Stars Twinkling Video" params="controls=0">}}

## Adaptive Optics
We implemented a fast **Adaptive Optics (AO)** system to correct these distortions in real-time in a small artificial channel in our lab. We use a "reference" laser beam to measure the distortions caused by turbulence in the channel at a given time. A "signal" beam carries the quantum information through the channel at the same time.

Here is a video showing off how a wavefront sensor works from the company we purchased out AO system from:


* **Measuring Turbulence - Shack-Hartmann Wavefront Sensor (SHWFS)**:  The reference beam is sent to a SHWFS to measure the phase changes caused by turbulence. These phase changes vary spatially, and you can consider the WFS to be a camera that exchanges position information in exchange for phase information.

{{<youtubeLite id="_IXWNkd4qHM"  label="SHWFS Video" params="start=24&mute=1">}}

* **Correcting Turbulence - Deformable Mirror**: The system uses a specialized mirror with 97 actuators that can change shape over 2000 times per second to counteract the specific wavefront errors measured by the SHWFS.

{{<youtubeLite id="YnoKBD6BJD4"  label="Deformable Mirror Video" params="start=25&mute=1">}}

## Key Results
Our experiments demonstrated that AO is very effective for maintaining a secure connection in turbulent environments:

* **Coupling Efficiency**: Without correction, turbulence reduced the average power reaching our detector to 36.6%. Activating the AO system increased this to **87.1%**, providing a stable and reliable signal.
* **Error Reduction**: We measured the **Quantum Dit Error Rate (QDER)** across various dimensions. Without AO, the error rates were so high that secure communication was impossible for any dimension greater than d=2. 
* **System Fidelity**: Through process tomography, we showed that AO restored the channel fidelity from under 50% to over **95%** in most cases. 
* **Secure Key Rates**: By reducing errors by an average of **32.5%**, we successfully established secure communication channels that would otherwise have failed.
* **Basis Preference**: One set of modes was more robust to turbulence, but was poorly corrected by our AO system. The other was very strongly affected by turbulence, but was well corrected by the AO system.

## Conclusion
This work proves that advanced adaptive optics can effectively mitigate the "smearing" effect of the atmosphere on structured light. These results are a promising step toward practical, high-speed quantum networks connecting ground stations to satellites, or even establishing secure links through other turbulent mediums like water.

---


{{<youtubeLite id="cRAmVcGRbr0"  label="HTSN Seminar Presentation">}}
A seminar where I talk about this work along with many others from the SQO research group.