# Training Pipeline Tab

## Input data type
Input data type specification allows you to optimize the preprocessing operation and reduce SRAM and Flash usage on the device and inference time. The data of the same type must be used for prediction. Neuton supports the following input data types: INT8, INT16, and FLOAT32. It is important to select the correct data type as incorrect selection of input data type may cause target metric degradation or total footprint increase. Select input data type according to the data type of all features in the training dataset. Keep in mind that you only need to choose one data type for the entire dataset. For example, if you have a dataset with three features and two of them are represented as INT16 while the third one is represented as FLOAT32, you should choose FLOAT32 as the data type for the entire dataset. The platform automatically determines the data type based on the logic discussed above. However, if the data type is not determined correctly, you can change it manually.
System uses the entire dataset to determine the data type.
8-bit Integer: The range of values in the dataset is from -128 to 127.
16-bit Integer: The range of values in the dataset is -32 768 to 32 767.
32-bit Floating point: At least one value in the dataset is a floating point number.

## Normalization type
This option allows you to select one of two scaling types for your dataset: "Unique scale for each feature" or "Unified scale for all features". For model training normalization is used, unique scaling for each feature may increase model predictive power as well as model footprint. Unified scaling may decrease model footprint. Everything depends on your dаta: it is better to use a "Unified scale for all features" when all values are on the same scale for all features.

## Raw Data option
Disabled by default: If enabled, raw data will be used for training. This setting applies to all variables and axes specified in the Feature Extraction block, meaning raw data can either be included for all variables and axes in the training dataset or excluded entirely. The Raw Data option can't be used when the sliding shift values differ from the window size values.