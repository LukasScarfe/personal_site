---
title: "Predicting atmospheric turbulence for secure quantum communications in free space"
date: 2025-03-03
summary: "We developed TAROQQO, a recurrent neural network that predicts atmospheric turbulence strength up to 12 hours in advance to optimize the timing of secure quantum key distribution."
showAuthor: false
showDate: true
showReadingTime: false
showWordCount: false
---

{{< katex >}}

## [**Click here for the full manuscript published in Optics Express**](https://doi.org/10.1364/OE.546606)

My work in the [SQO Group](https://sqogroup.ca/) led me to want to know if we could "see into the future" so that we could know whether or not we should do experiments on a given day. While previous work focused on cleaning up signals in real-time, this research introduces **TAROQQO**, a computational toolbox designed to predict when the atmosphere will be calm enough to establish a quantum key distribution channel in the first place.

## The Challenge: The Chaotic Atmosphere
Atmospheric turbulence is the primary obstacle for free-space quantum networks. Changes in the refractive index of air cause optical signals to experience scintillation, beam wander, and wavefront distortion. These effects are quantified by the structure parameter $C_{n}^{2}$.


{{<youtubeLite id="csqH3pNtFcI"  label="SQO Free Space Link">}}
 "**Channel path.** The path over which the turbulence data was collected from July 2023 to March 2024. The receiver is on the University of Ottawa campus, while the sender is on the Canadian National Research Council 5.4 km East-North-East."


In high-dimensional Quantum Key Distribution (QKD), where we use the spatial shape of light (like Orbital Angular Momentum) to send more data, even moderate turbulence can scramble the signal so much that the **Quantum Dit Error Rate (QDER)** exceeds the security threshold. Knowing the turbulence strength in advance allows us to route communications through the best available channels and avoid wasting resources during "bad weather" for quantum states.

## TAROQQO: Forecasting Turbulence
We trained a **Gated Recurrent Unit (GRU)** neural network, which we named **TAROQQO** (after the Italian word for tarot cards), to forecast the evolution of $C_{n}^{2}$ values.

### Data Collection
The network was trained on a massive dataset collected over **9 months** for a **5.4 km intra-city link** across the City of Ottawa. 
* **Sender:** Located at the National Research Council of Canada.
* **Receiver:** Located on the University of Ottawa campus.
* **Inputs:** We used minute-by-minute data including temperature, solar radiation, relative humidity, and historical turbulence values recorded by a scintillometer.


### Predictability
TAROQQO can output predictions up to **12 hours into the future** with a time resolution as fine as one minute. In our testing (using data from February and March 2024), the network achieved an average relative error of only **9%** on the actual $C_{n}^{2}$ values. Even during highly variable months like October, the network remained robust with approximately 20% error
{{< figure
    src="/img/predictions.png"
    alt="Predictions on one test set"
    caption="**Predictions on one test set.** Network predictions for the month from mid-February to mid-March 2024. We have our trained model forecast 6 hours in the future, then cascade individual predictions to cover one month. Jagged lines indicate missing data points from the scintillometer system. A one-hour moving average is applied to the training set to remove high-frequency noise. The scatter points refer to the raw data (before the moving average is performed). The insets show examples of individual 6-hour predictions, equally spaced throughout the month. Good performances are observed on average, with larger deviations occurring in correspondence with strong feature variations."
    >}}

## Simulated Quantum Experiments
To prove the utility of these predictions, we simulated an **8-dimensional BB84 QKD protocol** across the Ottawa channel. We compared two different ways of encoding information:
1.  **OAM Modes:** Circularly symmetric modes carrying orbital angular momentum.
2.  **ANGLE Modes:** A mutually unbiased basis that acts as the "Fourier-conjugate" to OAM.


### Key Findings
* **Security Thresholds:** We confirmed that secure communication is only guaranteed in the weak-turbulence regime ($C_{n}^{2} \approx 10^{-16}$). In strong turbulence ($C_{n}^{2} \approx 10^{-14}$), the error rates are too high for security.
* **Basis Robustness:** Interestingly, our simulations showed that the **ANGLE basis** is more robust than the OAM basis during moderate turbulence because it concentrates optical power in a smaller region.
* **Informed Decisions:** By combining TAROQQO's forecast with these simulations, a quantum network controller can predict the success rate of a key exchange before it even begins.

| Turbulence ($C_{n}^{2}$) | OAM QDER | ANG QDER | Key Rate (bits/photon) |
| :--- | :--- | :--- | :--- |
| $10^{-16}$ (Weak) | 8.18% | 2.33% | 2.11 |
| $10^{-15}$ (Moderate) | 77.00% | 41.47% | 0 |
| $10^{-14}$ (Strong) | 92.07% | 51.96% | 0 |

## Conclusion
TAROQQO provides a crucial validation step for near-term QKD experiments. By predicting the "quantum weather," we can optimize the use of time and resources, avoiding unfavorable conditions and ensuring that secure keys are only exchanged when the channel is reliable. This is a vital step toward practical ground-to-ground and ground-to-satellite quantum communication networks.

{{< figure
    src="https://raw.github.com/TareqJ1000/TAROQQO/tareq/TaroccoAI.png"
    alt="TAROQQO Tarot Card cover art"
    caption="TAROQQO Tarot Card cover art"
    >}}

---


{{<youtubeLite id="cRAmVcGRbr0"  label="HTSN Seminar Presentation">}}
A seminar where I talk about this work along with many others from the SQO research group.