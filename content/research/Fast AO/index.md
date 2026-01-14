---
title: "Fast adaptive optics for high-dimensional quantum communications in turbulent channels"
date: 2025-02-24
summary: "In this work, we showed that the use of a fast adaptive optics system in a high-dimensional quantum key distribution setup allows for secure communications even in the presence of significant noise ."
showAuthor: false
showDate: true
showReadingTime: false
showWordCount: false
---

{{< katex >}}

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

## Conclusion
This work proves that advanced adaptive optics can effectively mitigate the "smearing" effect of the atmosphere on structured light. These results are a promising step toward practical, high-speed quantum networks connecting ground stations to satellites, or even establishing secure links through other turbulent mediums like water.

---


{{<youtubeLite id="cRAmVcGRbr0"  label="HTSN Seminar Presentation">}}
A seminar where I talk about this work along with many others from the SQO research group.