# Questions & Answers addressed from support

## what does the subscribtion cost?
There is no subscription, the service is free for all.

## how to enable tinyML?
TinyML is a core of the platform, and there is no need to enable it. However, Neuton has a Digital Signal Processing option that helps you to preprocess raw data, which is necessary for tinyML use cases.

## how to use audio data?  
Neuton.ai currently does not support audio data.

## Can you self host the neuton trainer?  
Users can train models only using the Neuton.ai cloud platform.

## does neuton allow to train images?  
Unfortunately no, but working with images is included in our roadmap.

## can I use my own model architecture?
Neuton Neural Network Framework provides automatic neuron-by-neuron network structure growth, and allows for minimum-size models with excellent generalizing capability, and without a loss of accuracy. Neuton does not require predifined architecture definition, thus no network architecture input option is required/available.

## Your model training service seems to be cloud-based only. Do you provide it for on-prem servers as well?
On premises version is available on request. Please contact us at support@neuton.ai.

## Are the 8-bit models more accurate than the 16-bit ones. 
There is no such dependence. In many cases, the metrics of an 8-bit model may differ slightly from a 16-bit one, while the model itself will be more compact.

## Are the floating-point models more accurate than the integer-only ones?
It depends on the data. The model accuracy may remain the same or increase in the float-based model. It is more important that the integer-based model turns out to be more compact.

## why there are two numbers in the precision results  
When binary classification is used, the platform presents metrics for both classes.

## What kinds of datasets does your approach work on?
We work with time series sensor datat the moment. The images and audio data processing are in our roadmap. However, if your data is represented as numeric values, such as the MNIST dataset, you can train it on the platform.

## is it possible to run the c library generated on an arduino mega 2560?
For other Arduino boards, you need to adapt the c library.

## When selecting the sampling window, does the data get windowed in 1d or 2d?
The data gets windowed in 1d.

## Can I also upload data that is not csv?
You can upload your sensor data only in a .csv format or a zip archive with a single .csv dataset inside.

## Is there a sample around how the data should be formatted when having multiple features?
The data should be labeled and placed in one .csv file. Please, refer to our [user guide](https://neuton.ai/st/95-dataset-requirements.html) for details. You can also check our [Use Cases section](https://lab.neuton.ai/#/cases) on the platform.

## hello, how can I close the account?
You may request to delete your account at any time and for any reason by contacting our support team at support@neuton.ai. Once we receive your request, we will promptly begin the process of deleting your account along with all associated Neuton Service Data, in accordance with any applicable legal data retention requirements. You will receive a confirmation email once the deletion is complete.

## How to unsubscribe?
You can send an unsubscribe request to https://neuton.ai/contactus

## For testing in Neuton, should I combine all CSV files for a given feature into one?
Yes, this is the only way you can feed the data on the platform.  

## Should there be a timestamp column in the data or not?
nope, you can and should exclude it, because no signal-defining features could be extracted from timestamp.

## Is it necessary to explicitly specify the start and end of each sample in the data, or can the system infer this information from patterns?
In case each CSV contains continuous measurements of a single activity - you should add a ‘target’ column to indicate that activity. So for example your first CSV contains readings of running and you’ve been collecting only the accelerometer data. In this case you should add a column ‘target’ which will indicate the integer code for running. In this case, your dataset will have 4 columns: acc_x, acc_y, acc_z, and target. And the target will all be the same in this particular dataset indicating that all this data reflects the running activity. When you concatenate all your activities (don’t shuffle any of the data) into a single dataset - based on the target column and the ‘window’ value the platform will sort everything else out automatically.

## How do I upload test data to validate against?  
To enable holdout validation and upload a holdout validation dataset - turn on the toggle near holdout validation on the Dataset tab. After the model training completion, metrics will be calculated on the holdout dataset. The holdout validation dataset must be in the same format (same column names) as the training dataset.

## im going my training on a runpod, using a docker image with jupyter, is there an access point for your service that will allow me to connect directly or do i have to store my files on google and push them through that way?
Neuton.ai currently does not provide API access for training. You need to use the platform.

## How do I start training on the Neuton platform?
To start training, you must manually upload the dataset to the Neuton platform and configure the solution.

## What should I do if I have any questions?
If you have any questions, please feel free to contact us. We will be happy to help!

## How do I use the solution I downloaded on an Arduino?
You can find a guide [here](https://neuton.ai/st/101-run-inference-on-the-mcu.html) At present, the [project](https://neuton.ai/news/projects/113-ultra-tiny-solution-of-daily-activities-recognition.html) works with Nicla Sense ME without improvements. For other Arduino boards, you need to adapt the c library.

## Hi I am trying to upload previous loaded .cvs file for training dataset, but now your system shows error. Can you tell me why?
According to our logs, your dataset has not enough samples. For your experiment (window size = 128), you need at least 6400 rows of samples in your dataset. 451 rows are not enough for Neuton to process the dataset. However, you can try to reduce the window size and repeat your experiment. Also, judging by our logs, the target variable is represented with only one class instead of two. We recommend you add the second possible outcome to your target variable.

## Hi, does work on arm only or can run the generated library on my intel cpu?
We offer a downloadable C library compatible with the following platforms: Cortex M0, Cortex M4, Cortex M33, STMicro ISPU, and Microchip-8 series. To run inference on an intel cpu (PC) you can use the inference_runner CLI tool located in the artifacts directory in the downloadable archive.

## is there a tutorial on how to integrate Neuton in stm32 ispu?
Follow the README.md file in the X-CUBE-ISPU expansion package (en.x-cube-ispu.zip\Ispu\) for the development environment setup.

## I wanted to follow up on a question I submitted through your contact us page regarding getting a pre-compiled library for the ARC EM4 mcu.
We will be happy to meet and learn about the project you are working on. Please feel free to contact us at support@neuton.ai. We will be happy to help!

## I have a question about the neuton libraries, are they available only for the cortex M4 and the cortex M0?
We offer a downloadable C library compatible with the following platforms: Cortex M0, Cortex M4, Cortex M33, STMicro ISPU, and Microchip-8 series. 

## how I can see the models footprint running on an ispu? I can only see m4 and m0.
Unfortunately, this feature is still in development. However, you can view the total footprint by embedding the model in the STMicro ISPU.

## When I link the neuton's libneuton_arm_cm4.a with my project, I get errors like: uses VFP register arguments, firmware.elf does not. Is there a way to overcome this?
answer
It seems like yours is compiled with mfloat-abi=softfp and there could be a mismatch because of that. Our library is compiled with -mfloat-abi=hardfp, but Arduino by default compiled with mfloat-abi=softfp, that's why you have this mismatch-mthumb-mcpu=cortex-m4-mfloat-abi=hard-mfpu=fpv4-sp-d16.

## Hi, can I use neuton to run on ESP32?  
Absolutely. 

## Can I upload data for you to do modelling?  
Absolutely. Could you kindly provide details about your data and the specific task you are attempting to accomplish? Please use support@neuton.ai for further communication.

## could you tell me why my training stopped? 
Typically, such errors happen if the requirements for the dataset are not met. Based on our logs, your window size is 52. This means that your data (time series) must contain consecutive readings first from one class, then from another class, then from the third class and so on; and when a window of 52 is applied to the dataset, it will capture consecutive sensor readings for 52 rows of one event many times, then of another event and so forth. The log says that the preprocessed dataset contains 0 records. This usually means that the original data does not have a single event where sensor readings for any class contained a consecutive number of records of window size (52 in your case). 

## is it possible i train the model myself and upload it?
Unfortunately, it is not possible to upload your own model to the platform. However, we suggest trying out our platform to create ultra-tiny machine learning models using the Neuton technology.

## any deployment tutorial?
Sure, you can find a Readme file in the downloadable archive. Please check the [tutorial](https://neuton.ai/st/101-run-inference-on-the-mcu.html)

## my device is cortex m3, is it possible to use neuton? cause i getting error when adding the m0/m4 lib
The platform offers a downloadable C library for Cortex M0, Cortex M4, Cortex M33, Microchip 8-series and STMicro ISPU. 

## I have the database, how to apply  
If you want to upload data for model training, you need to prepare your data in CSV format. You can find more information about the dataset requirements [here](https://neuton.ai/st/95-dataset-requirements.html). You can also find guidance on how to upload your data [here](https://neuton.ai/st/96-data-uploading-and-setup.html).

## Hello, is there any docs that I can follow to try the model in raspberry pi 4?
Please refer to our user [guide](https://neuton.ai/st/101-run-inference-on-the-mcu.html)

## So for Cortex-A72, will it be available?
Sure, kindly send us a request at support@neuton.ai, and the team will respond as soon as they can.

## Is there any forum, where I can ask questions specific to my problem?
Unfortunately, we don't have any forums, but you can ask any questions related to the Neuton platform here or write to support@neuton.ai

## Can I test this code on my desktop?
If you want to run inference on your PC, it is possible. Please refer to the user [guide](https://neuton.ai/st/111-desktop-executable-prediction.html

## After training, how to see the Neural Network Structure  
We do not provide the option to view or manually edit the Neural Network Structure.

## Can i use ESP32 Cam to detect fish movements
Unfortunately, ESP32-CAM cannot be utilized with Neuton as the platform is not designed to support video data

## I'm having some problems integrating the C library into the Arduino IDE. Can you help me or explain in detail how I need to include the library correctly.
Unfortunately, we do not currently offer support for the Arduino IDE, which may be the reason for the issue you are experiencing.

## Which development environments do you support? Can I use the C library with Visual Studio Code to program the Arduino Nano 33?
While we don't currently support native integration with the Arduino environment, if you are able to link our library yourself, you should be able to make it work for Arduino Nano 33.

## I got a message that "Creation of the neural network structure for CPWatcher has completed" and after that "Training stopped", do I need to do anything in order to continue?
We are pleased to hear that you were able to successfully train the model with such high accuracy. You can proceed to the Results tab on the platform to access training results and download the trained model archive.

## Why my training always get stopped  
Your dataset does not have enough samples for each class. Ideally, there should be at least 20 samples for each of the classes. Additionally, your dataset has already been preprocessed, so there is no need to use the Digital Signal Processing (DSP) option when selecting training settings. You need to add more samples for each class and disable the DSP option when selecting training settings. Once you have made these changes, you can start training again.

## Do you have any idea about how do I use neuton_nn_setup() in arduino?
Please check out our user [guide](https://neuton.ai/st/101-run-inference-on-the-mcu.html) on how to embed Neuton's models. However, we don't currently support native integration with the Arduino environment.

## How do I use the model on atmega128rfa1 MCU?
If you're interested in more customization options or different libraries. To learn more and express your interest, please contact us at support@neuton.ai.

## are you using pruning?
Neuton is based on a unique patented machine learning algorithm that forgoes error backpropagation and stochastic gradient descent, growing the network structure neuron by neuron. This helps to build neural networks without compromising between accuracy and size:, with the excellent generalizing capability; with minimal size, often less than 1 Kb; without loss of accuracy; without compression techniques. Neuton models maintain all of their original characteristics, without any reduction of accuracy. Neuton does not reduce the model size after its creation. Neuton does not use quantization, pruning, clustering, nor distillation.

## i have a problem including the neuton library in the arduino ide. I need the procedure to include the library in ide.
While we don't currently support native integration with the Arduino environment, if you can link our library yourself, you should be able to make it work for Arduino. We plan to include support for the Arduino environment in our forthcoming updates.

## Is there a way to retrain the same model from the inference runner executable?
The Inference Runner Executable enables you to validate the results of the model's inference without requiring implementation on the Edge device exclusively. If you intend to retrain the model, you'll need to create a new solution and conduct the training process anew. Also, you can copy your existing solution to avoid reconfiguring the same settings.

## Is there any positive and negative coefficient show in the model?  
The structure of the model is not revealed on the platform because Neuton is a proprietary neural network framework. However, you can assess the number of coefficients in the trained model on the platform's Results tab.

## do this cost any money?  
No, it is free for all!

## I would like to know if we can use Neuton to create a model and put it into our product, it is a smart ring and we are a start-up, we are planning to sell the smart ring to our customers, can we use your platform to create a production model for a commercial product?
We would love to consult you personally. Please drop us a message at support@neuton.ai.

## Hey anyway how can i integrate my model to micropython?
Our model is run by using a C API. If you're able to call our model API using C from MicroPython using some subprocess, you can receive predictions by providing sensor data to the Neuton library. In the model archive, there's an "inference_runner" folder which includes a CLI tool for getting predictions. Try running it using a subprocess from MicroPython and then update us on how it went.

## Is input[0] meant to be ax and field 6 is irrelevant? Is input[0] irrelevant and input[6] gz?  
Did you by chance have an index column in your dataset? E.g.: If you are working with 6 axis then your dataset should have 7 columns: acc_x, acc_y, acc_z, gyro_x, gyro_y, gyro_z, target. Regardless of the use-case or the type of sensor data your dataset should not contain an index/timestamp column.

## can i upload data in pdf and other text formats, or can neuton fetch pdfs from my google drive to learn before responding?
Neuton currently accepts data in the .csv format.

## how can neuton help me set up a neural network to predict anticompetitive behaviour by plcs?
Neuton offers sophisticated features for developing precise and highly compact models using sensor data for EDGE devices. 

## Where is the HQ of neuton.ai  
Our headquarters is located at 6200 Stoneridge Mall Rd Ste 300, Pleasanton, CA 94588, USA.

## Is there mobile version of neuton ai  
Our platform is currently designed for desktop use and does not support a mobile version at this time.

## can this app solve coding errors?
Neuton TinyML is not specifically designed to solve coding errors. Its primary focus is on developing machine learning models for edge devices, which can be used in a variety of applications but not directly for debugging or fixing coding errors in software development.

## how can i try a pretrained model  
To try a pretrained model on the Neuton platform, you can start by exploring the test-drive version, which is free for developers worldwide. Here's how you can get started: Registration: Sign up on the Neuton platform using the following [manual](https://neuton.ai/st/87-how-to-subscribe-to-neuton.html). Explore Preloaded Datasets: Once registered, you can explore preloaded datasets available on the platform. This allows you to understand how models are built and tested.