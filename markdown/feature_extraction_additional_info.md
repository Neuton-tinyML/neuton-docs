# Feature Extraction

When the window size is specified, the platform automatically extracts the selected features for each column in the training dataset. The same feature extraction will be automatically executed during inference on the device. You can manage calculated features for each original variable in the training dataset by marking or unmarking the appropriate checkbox. To disable a variable/axis from the Feature Extraction block, use the "Edit" button, which appears when hovering over a feature. After doing so, no feature will be created for it, and therefore it will not participate in building the model. By default, Feature Extraction uses all variables/axes. To select all available features, click the "Select All" button. To revert to the original settings, click the "Back to Default Settings" button. If you are looking for a particular feature, you can use the search bar to locate it.

## Time-domain features

### Kurtosis 
Statistical measure of the combined weight of a distribution's tails relative to the center of the distribution.\

### Max
Statistical function that calculates the maximum of the column (feature).

### Mean
Statistical function that calculates the arithmetic mean of the column (feature).

### Mean Crossings
Statistical function that calculates the number of times the selected column crosses the mean.

### Min
Statistical function that calculates the minimum of the column (feature).

### Negative Mean Crossings
Computes the number of times the selected input crosses the mean with a negative slope.

### Positive Mean Crossings
Computes the number of times the selected input crosses the mean with a positive slope.

### Root Mean Square
Root of the arithmetic mean of the squares of a set of numbers.

### Skewness
Statistical function measures the asymmetry of the distribution of a variable.

### Variance
Statistical function that calculates the minimum of the column (feature).

### Low/High frequency energy ratio
A signal processing technique used to analyze and characterize sensor data, particularly in applications involving vibration monitoring, acoustic analysis, and fault detection. This method compares the energy content of low-frequency components to high-frequency components within a signal.

### Absolute Mean
Average of the absolute values of its samples, it measures the average signal magnitude, ignoring polarity (positive or negative values), t's a simple way to estimate signal energy and intensity, similar to RMS but less compute intensive.

### Average Magnitude Difference
AMDF is a signal processing technique used for periodicity analysis in sensor signals. AMDF is particularly useful in applications such as speech analysis, music signal processing, and other sensor-based systems where detecting periodic patterns is crucial. However, it may suffer from incorrect pitch detection in highly noisy conditions, which has led to the development of extended versions of AMDF for improved performance.

### Percentage of signal over mean
Ratio between number of sensor signal values being greater than the mean value in a window over the total window size.. The Percentage of Signal Over Mean is particularly useful in applications where relative changes in the signal are more important than absolute values, such as in vibration analysis, environmental monitoring, or process control systems.

### Mean Absolute Deviation
MAD is a feature extraction technique used in sensor signal processing to quantify the variability or dispersion of a signal. It is calculated as the average of the absolute differences between each data point and the mean of the dataset

### Percentage of signal over zero
Ratio between number of positive sensor signal values in a window over the total window size. In other words - time a signal was positive.

### Range
Difference between the maximum and minimum values of a signal within a given time window or measurement period. It is a simple yet informative feature that provides insight into the signal's amplitude variation.

### Zero-crossing Rate
ZCR is defined as the number of times a signal changes its sign from positive to negative or vice versa, divided by the length of the frame. In other words, it represents the frequency with which the signal crosses the zero axis.

### Crest factor
Ratio of a signal's peak amplitude to its root mean square (RMS) value, particularly useful for analyzing waveforms in various applications such as electrical engineering, audio processing, and vibration analysis.

### Percentage of signal over sigma
Ratio between number of sensor signal values being greater than the sigma value (mean + n standard deviations ) in a window over the total window size.

### Positive sigma crossing rate
Measures how frequently a signal exceeds a threshold defined as a multiple of the standard deviation (σ) above the mean. This feature helps identify significant deviations in signal amplitude and is particularly useful for detecting repetitive patterns or anomalies in time-series data.

### Root Difference Square
Measures the square root of the mean squared difference from the signal neighboring discrete points, it measures mean signal variation between neighboring points, can be used as a characteristic of the rate of change of a signal. (edited) 

### Standard Deviation
Quantifies the amount of variation or dispersion in a set of data points from their mean value. In feature extraction, standard deviation is often used alongside other statistical measures such as mean, variance, skewness, and kurtosis to provide a comprehensive representation of signal characteristics. It's particularly useful in: Activity recognition: Helping distinguish between high-variance and low-variance movements in wearable devices. Audio processing: Measuring the dynamic range of audio signals. Image processing: Extracting texture features from images. Anomaly detection: Identifying unusual patterns or outliers in data."

### Threshold-crossing Rate
TCR is a feature extraction technique used in digital signal processing and time series analysis. It measures the frequency at which a signal crosses a predefined threshold value within a given time window.

### Autocorrelation
Powerful statistical technique used in feature extraction for signal processing and time series analysis. It measures the correlation between a signal and a time-shifted version of itself, providing valuable insights into the signal's inherent patterns, periodicities, and statistical properties.

### Global peak to peak of high frequency
Maximum variation in amplitude of the high-frequency components across the entire signal. Based on the available information, we can infer some relevant concepts: 
1. High-frequency feature extraction: This involves isolating and analyzing the high-frequency components of a signal. It's often used in image processing, audio analysis, and vibration monitoring. 
2. Peak-to-peak amplitude: This measures the difference between the maximum and minimum values of a signal over a given interval. In the context of high-frequency analysis, it would refer to the largest variation in the high-frequency components of the signal."

### Global peak to peak of low frequency
Maximum variation in amplitude of the low-frequency components across an entire signal. This feature provides valuable information about the overall intensity and range of low-frequency content in a signal. This feature is particularly valuable in applications where understanding the range and intensity of low-frequency components is crucial, such as in vibration analysis, audio engineering, and various scientific and industrial monitoring systems.

### Hjorth Complexity
Measures the change in frequency—i.e., how the shape of the signal evolves. The parameter compares the signal's similarity to a pure sine wave, where the value converges to 1 if the signal is more similar. In the robotic area, the Hjorth parameters are used for tactile signal processing for the physical object properties detection such as surface textures/material detection and touch modality classification via artificial robotic skin.

### Hjorth Mobility
Measures the mean frequency or the rate of change of a signal, tells how fast the signal changes. This is defined as the square root of variance of the first derivative of the signal y(t) divided by variance of the signal y(t). In the robotic area, the Hjorth parameters are used for tactile signal processing for the physical object properties detection such as surface textures/material detection and touch modality classification via artificial robotic skin.

## Frequency-domain features
These functions use Fast Fourier transform to calculate the frequency of peaks and their power. If frequency features are selected, the window size should be equal to the power of 2. If Frequency domain features are selected (at least one), then the window size must be: >= 128 samples, <= 2048 samples, equal to the power of 2.

If the user first enters Min/Max Window size, then selects Frequency features: The system checks that the window size is ≥ 128 samples, ≤ 2048 samples, and is a power of 2; If the window size doesn't meet these conditions, the system will show a popup to resize the window.

If the user first selects Frequency features and the Window size is empty: The system will display a popup to resize the window.

If the user ha selsected Frequency features, then edits the window size: The system checks that the window size is ≥ 128 samples, ≤ 2048 samples, and is a power of 2; If the window size doesn't meet these conditions, the system will unselect Frequency features.

### Amplitude spectrum
Crucial feature extraction technique in signal processing that provides valuable information about the frequency content of a signal. It represents the magnitude of different frequency components present in a signal, offering insights into its spectral characteristics. The amplitude spectrum is particularly valuable in applications requiring frequency domain analysis, such as speech recognition, vibration analysis, and signal classification tasks. Its ability to reveal the underlying frequency structure of signals makes it an essential tool in modern signal processing and feature extraction workflows.

### Dominant Frequency Amplitudes
DFAs are important features extracted from signals in frequency domain analysis. They represent the amplitudes of the most prominent frequency components in a signal's spectrum, enabling efficient representation and analysis of complex waveforms.

### Dominant Frequency Mean Distance
DFMD is a feature extraction metric that quantifies the average separation between dominant frequency components in a signal or across signal segments. It is particularly useful for analyzing temporal or spatial variations in frequency characteristics. Typical applications: In rotating machinery, a high DFMD indicates irregular vibration patterns (e.g., bearing wear); Track DF variations in EEG/ECG to detect arrhythmias or seizures; Monitor frequency drift in wireless signals.

### Dominant Frequency SNR
Dominant Frequency Signal-to-Noise Ratio (DF SNR) represents the ratio of the power of the dominant frequency component to the power of the noise in a signal. Potential applications are vibration analysis and anomaly detection.

### Dominant Frequency THD
Total Harmonic Distortion (THD) combined with dominant frequency analysis is a critical method for evaluating signal quality in sensor applications. THD quantifies harmonic distortion by comparing the energy in harmonic frequencies to the fundamental (dominant) frequency, while the dominant frequency represents the primary oscillation component in a signal. Applications: System Characterization: Quantifies spurious emissions in RF sensors and distortion in pressure/acceleration sensors. Condition Monitoring: High THD in vibration sensors indicates bearing wear or mechanical faults. Signal Filtering: Helps design notch filters to suppress harmonics in ECG/biomedical sensors."

### Dominant frequencies
Most prominent frequency components within a signal's spectrum, identified through frequency-domain analysis. These frequencies are critical for interpreting physical phenomena, system behaviors, or material properties across diverse applications like biomedical sensing, geophysical surveys, and fluid dynamics. Applications: Biomedical Signals: In atrial fibrillation studies, dominant frequencies help map arrhythmia drivers (e.g., 4–9 Hz frequencies indicating rapid atrial activity). HRV analysis uses LF (0.04–0.15 Hz) and HF bands to assess autonomic nervous system balance. Geophysical Sensing: Ground-penetrating radar (GPR) identifies soil moisture or material boundaries by linking dominant frequencies to subsurface reflections. Fluid Dynamics: Dominant frequencies in particle image velocimetry (PIV) data reveal vortex shedding patterns around airfoils."

### Low/Mid frequency energy ratio
Feature extraction technique used in signal processing to analyze the distribution of energy between lower and mid frequency bands of a signal. This metric provides valuable insights into the spectral characteristics of various signals, including audio, vibration, and electrical signals. Applications:  Audio Processing: Distinguishing between different types of audio signals, such as speech and music. Vibration Analysis: Identifying mechanical faults or system characteristics in structural dynamics. Power Quality Monitoring: Detecting and classifying voltage sags and other power disturbances.

### Mid/High frequency energy ratio
Feature extraction technique used in audio signal processing to analyze the distribution of energy between mid-range and high-frequency components of a signal. This metric is similar to the low/high frequency energy ratio but focuses on a different part of the frequency spectrum. Applications: Audio classification and genre detection; Speech processing and recognition; Musical instrument identification; Acoustic event detection.

### Spectral Centroid
Key feature extraction technique used in digital signal processing to characterize the spectral content of high frequency signals. It represents the center of mass of a spectrum and is closely associated with the perceived brightness of a signal. Applications:  The spectral centroid is widely used in: Audio classification and genre detection;  Speech processing and recognition; Musical instrument identification; Timbre analysis in music processing.

### Spectral Crest
Feature extraction technique used in signal processing to measure the peakiness or tonality of a signal's spectrum. It is calculated as the ratio of the maximum magnitude in the spectrum to the arithmetic mean of the spectrum. Applications: Audio classification and genre detection; Instrument recognition; Voiced/unvoiced speech classification; Audio scene recognition.

### Spectral RMS
Spectral RMS (Root Mean Square) is a feature extraction technique used in signal processing to measure the average energy of a signal in the frequency domain. It provides valuable information about the spectral content and overall power of an signal. Applications: Spectral RMS is used in various audio processing tasks: Audio classification and genre detection; Speech processing and recognition; Music analysis and instrument identification; Audio quality assessment.

### Spectral Spread
Feature extraction technique used in signal processing to measure the dispersion of the spectrum around its centroid. It is calculated as the average deviation of the spectrum from its spectral centroid. It is commonly used in various audio analysis tasks, including: Audio classification and genre detection; Speech processing and recognition; Musical instrument identification; Voice activity detection.
