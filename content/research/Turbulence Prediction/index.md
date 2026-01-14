---
title: "Predicting atmospheric turbulence for secure quantum communications in free space"
date: 2025-03-03
summary: "Atmospheric turbulence represents the primary obstacle to the implementation of large-scale free-space quantum communication networks because environmental aberrations distort the optical information carriers and limit the ability to establish secure links between distant parties. In this research paper, the authors introduce a recurrent neural network called TAROQQO specifically designed to forecast turbulence strength within an optical channel to identify the optimal timing for secure communication. The study is grounded in a robust dataset of weather and turbulence parameters collected over a nine-month period across a 5.4-kilometer intra-city free-space link in Ottawa, Canada. Unlike previous empirical models or neural networks that were limited by seasonal data or fixed-time predictions, TAROQQO offers a flexible computational toolbox capable of outputting predictions up to twelve hours in advance with a minute-by-minute time resolution. This high resolution is critical for capturing the rapid temporal variations in the refractive index, quantified by the structure parameter, which causes scintillation, beam wandering, and wavefront distortion. To demonstrate the practical implications of these predictions, the researchers performed numerical simulations of a high-dimensional quantum key distribution protocol using the BB84 framework. This protocol utilized spatial modes of light, specifically orbital angular momentum states, which are highly sensitive to atmospheric conditions. By analyzing the performance of these states across different turbulence regimes, the authors were able to infer a specific turbulence threshold under which a real-world experiment can be conducted successfully. The simulation results showed how aberrations induce crosstalk and reduce power transmission, but by using TAROQQO to predict the channel's behavior, researchers can make informed decisions about when to initiate a key exchange. This predictive capability optimizes the use of experimental resources and reduces costs by avoiding periods of unfavorable atmospheric conditions. The study highlights that the network's training on real night-time and multi-season data allows it to generalize effectively across varying environmental states. Furthermore, the researchers suggest that while the primary focus is on quantum key distribution, the TAROQQO framework is broadly applicable to any free-space optical experiment involving structured light or satellite-to-ground communication. The paper concludes that integrating recurrent neural networks into the management of quantum networks is a vital step toward reliable ground-to-ground and ground-to-satellite configurations. By providing a method to validate the turbulent channel in advance, the authors have created a tool that ensures secure communication links are only established when the atmospheric conditions permit high-fidelity transmission. This research ultimately bridges the gap between theoretical quantum communication and the practical challenges of deploying such technologies in unpredictable urban environments, offering a path forward for more resilient and efficient quantum networking infrastructure. Through the combination of longitudinal environmental sensing and advanced machine learning, the work provides a comprehensive strategy for overcoming the stochastic nature of the atmosphere in the pursuit of secure global communication."
showAuthor: false
showDate: true
showReadingTime: false
showWordCount: false
---

{{< katex >}}

{{< dynamic-img 
    light="https://raw.githubusercontent.com/LukasScarfe/Google-Scholar/refs/heads/master/plots/light/Predicting_atmospheric_turbulence_for_secure.png"
    dark="https://raw.githubusercontent.com/LukasScarfe/Google-Scholar/refs/heads/master/plots/dark/Predicting_atmospheric_turbulence_for_secure.png"
    alt="Citation Count"
    caption=" [Source](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=_eBW18oAAAAJ&citation_for_view=_eBW18oAAAAJ:zYLM7Y9cAGgC)" 
>}}

## [**Click here for the full manuscript published in Optics Express**](https://doi.org/10.1364/OE.546606)

My work in the [SQO Group](https://sqogroup.ca/) led me to want to know if we could "see into the future" so that we could know whether or not we should do experiments on a given day. While previous work focused on cleaning up signals in real-time, this research introduces **TAROQQO**, a computational toolbox designed to predict when the atmosphere will be calm enough to establish a quantum key distribution channel in the first place.

## The Challenge: The Chaotic Atmosphere
Atmospheric turbulence is the primary obstacle for free-space quantum networks. Changes in the refractive index of air cause optical signals to experience scintillation, beam wander, and wavefront distortion. These effects are quantified by the structure parameter \(C_{n}^{2}\).


{{<youtubeLite id="csqH3pNtFcI"  label="SQO Free Space Link">}}
 "**Channel path.** The path over which the turbulence data was collected from July 2023 to March 2024. The receiver is on the University of Ottawa campus, while the sender is on the Canadian National Research Council 5.4 km East-North-East."


In high-dimensional Quantum Key Distribution (QKD), where we use the spatial shape of light (like Orbital Angular Momentum) to send more data, even moderate turbulence can scramble the signal so much that the **Quantum Dit Error Rate (QDER)** exceeds the security threshold. Knowing the turbulence strength in advance allows us to route communications through the best available channels and avoid wasting resources during "bad weather" for quantum states.

## TAROQQO: Forecasting Turbulence
We trained a **Gated Recurrent Unit (GRU)** neural network, which we named **TAROQQO** (after the Italian word for tarot cards), to forecast the evolution of \(C_{n}^{2}\) values.

### Data Collection
The network was trained on a massive dataset collected over **9 months** for a **5.4 km intra-city link** across the City of Ottawa. 
* **Sender:** Located at the National Research Council of Canada.
* **Receiver:** Located on the University of Ottawa campus.
* **Inputs:** We used minute-by-minute data including temperature, solar radiation, relative humidity, and historical turbulence values recorded by a scintillometer.


### Predictability
**TAROQQO** can output predictions up to **12 hours into the future** with a time resolution as fine as one minute. In our testing (using data from February and March 2024), the network achieved a low averade deviation when comparing the predictions to the actual measured values. It is hard to quantify exactly, but if you look at the below plot, you can very nicely qualitatively see how well **TAROQQO** is working
{{< figure
    src="img/predictions.png"
    alt="Predictions on one test set"
    caption="**Predictions on one test set.** Network predictions for the month from mid-February to mid-March 2024. We have our trained model forecast 6 hours in the future, then cascade individual predictions to cover one month. Jagged lines indicate missing data points from the scintillometer system. A one-hour moving average is applied to the training set to remove high-frequency noise. The scatter points refer to the raw data (before the moving average is performed). The insets show examples of individual 6-hour predictions, equally spaced throughout the month. Good performances are observed on average, with larger deviations occurring in correspondence with strong feature variations."
    >}}

## Simulated Quantum Experiments
To prove the utility of these predictions, we simulated an **8-dimensional BB84 QKD protocol** across the Ottawa channel. We compared two different ways of encoding information:
1.  **OAM Modes:** Circularly symmetric modes carrying orbital angular momentum.
2.  **ANGLE Modes:** A mutually unbiased basis that acts as the "Fourier-conjugate" to OAM.


### Key Findings
* **Security Thresholds:** We confirmed that based on our experimental parameters, secure communication is only guaranteed in the weak-turbulence regime \(C_{n}^{2} \approx 10^{-16}\). In strong turbulence \(C_{n}^{2} \approx 10^{-14}\), the error rates are too high for security.
* **Basis Robustness:** Interestingly, our simulations showed that the **ANGLE basis** is more robust than the OAM basis during moderate turbulence because it concentrates optical power in a smaller region. [This actaully confirms a secondary finding of a previous experiment]({{< ref "/research/Fast AO/index.md/#Key Results" >}})
* **Informed Decisions:** By combining **TAROQQO**'s forecast with these simulations, a quantum network controller can predict the success rate of a key exchange before it even begins.

| Turbulence (\(C_{n}^{2}\)) | OAM QDER | ANG QDER | Key Rate (bits/photon) |
| :--- | :--- | :--- | :--- |
| $10^{-16}$ (Weak) | 8.18% | 2.33% | 2.11 |
| $10^{-15}$ (Moderate) | 77.00% | 41.47% | 0 |
| $10^{-14}$ (Strong) | 92.07% | 51.96% | 0 |

## Conclusion
**TAROQQO** provides a crucial validation step for near-term QKD experiments. By predicting the "quantum weather," we can optimize the use of time and resources, avoiding unfavorable conditions and ensuring that secure keys are only exchanged when the channel is reliable. This is a vital step toward practical ground-to-ground and ground-to-satellite quantum communication networks.

{{< figure
    src="https://raw.github.com/TareqJ1000/TAROQQO/tareq/TaroccoAI.png"
    alt="**TAROQQO** Tarot Card cover art"
    caption="**TAROQQO** Tarot Card cover art"
    >}}

---


{{<youtubeLite id="cRAmVcGRbr0"  label="HTSN Seminar Presentation">}}
A seminar where I talk about this work along with many others from the SQO research group.