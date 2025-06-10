# Windowing

## Description
Window size is the portion of data that will be used for processing the training dataset (the static window approach is applied on the platform). It should be universal for all events in the training dataset, even if the duration of events is different. Therefore, for correct training of the model, the data in the training and the validation datasets (if applicable) must be brought to the same window using upsampling or downsampling, before loading into the platform. Using the window size, the training dataset will be grouped by a selected number of samples. All variables extracted from the raw data will be calculated from these groups. For correct feature calculation, the recommended minimum window size is 5 samples/rows. Since the platform is intended for solving TinyML tasks, it is recommended that the maximum window size does not exceed 1000 samples/rows. However, it all depends on your data and there are no technical restrictions on the window size in the platform.

## Number of rows option
Number of Rows option: select the integer number of rows based on your domain knowdedge. For example if your data is sampled at 100Hz and you know that the longest activity in your dataset takes no longer than 1 second to execute, then you 100 rows would be a viable option. If at least one frequency domain feature is selected, the window size in samples must meet the following conditions:
1. It must be a power of 2.
2. It must not be less than 128 samples.
3. It must not exceed 2048 samples.

## Time Interval option
Specify the window size in milliseconds (ms) and the frequency in Hertz (Hz) to define the window size for the training dataset. If you are using sensors with different frequencies, you must first bring all signals to a single frequency through downsampling or upsampling. Based on the specified data, the platform will automatically calculate the window size in rows/samples, which will be used for feature calculation and other operations. If frequency domain features are selected (at least one), the window size must satisfy the following conditions:
1. Frequency×Window size in ms/1000 must be a power of 2 (or the window size in samples must be a power of 2).
2. The window size must be no lower than 128 samples and no more than 2048 samples.

## Auto Determination option
Specify window size boundaries, frequency and sliding shift in %.
1. The minimum window size cannot exceed the maximum window size.
2. If the user enters a minimum value greater than the maximum value, the system will automatically adjust the minimum value to the default.
3. If the user enters the minimum value equal to the maximum value, this is allowed, and the window size will be determined as per the user input.

# Sliding Shift

## Description
The sliding shift is used for the window overlap and indicates how many rows/samples are needed to shift to form the next window. It is available for both training and inference. If the sliding shift values are equal to the window size, then the window segmentation is performed without an overlap. The options' value can't exceed the specified window size. When windowing auto-determination is enabled, the sliding shift values are set automatically equal to the window size.

## Implications
Estimated SRAM Usage: SRAM depends on the window size you choose and the list of features that will be created from the raw data. This calculation is tentative. The exact values will be computed after training the model and compiling the C libraries for specific hardware types. If you select auto-determination for the window, the estimated SRAM usage will not be calculated, as the platform determines the window size only after training begins. The system will display the message: "Windowing auto determination enabled."