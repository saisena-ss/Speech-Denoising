# Speech-Denoising

### Introduction
In this project, I tackle the task of speech denoising using Recurrent Neural Networks (RNNs). The primary objective is to train an RNN to estimate Ideal Binary Masks (IBM) for given spectrograms. These IBM matrices are used to distinguish between speech and noise elements in the time-frequency domain of audio signals. The trained RNN will learn to approximate this masking operation, enabling the denoising of noisy speech signals.

### Problem Statement
In many real-world scenarios, audio recordings are contaminated with background noise, making it challenging to extract the desired speech signals. The goal is to develop a neural network model that can effectively separate speech from noise, enhancing the signal quality.

### Solution
Ideal Binary Masks (IBM)
IBM matrices are binary masks that indicate whether each time-frequency bin in a spectrogram corresponds to speech (1) or noise (0).
These masks can be constructed by comparing the magnitude of the speech signal (S) to the magnitude of the noise signal (N) in the time-frequency domain.
#### RNN-based Speech Denoising
I used RNNs to learn the relationship between noisy spectrograms (X) and the corresponding IBM masks (M).
The RNN will predict the binary masks that best separate speech and noise components from the input spectrograms.

### Implementation
1. Dataset
Prepare a dataset containing pairs of noisy spectrograms (X) and their corresponding IBM masks (M).
Ensure that the dataset includes both training and validation sets.
2. RNN Architecture
Design a simple RNN architecture. Starting with a small network is recommended.
The RNN should take the noisy spectrogram as input and predict the IBM mask as output.
3. Training
Train the RNN using the training dataset.
Use a suitable loss function, such as binary cross-entropy, to measure the dissimilarity between predicted masks and ground truth IBM masks.
Monitor the training process, including the loss curve, to assess the model's convergence.
4. Validation and SNR Evaluation
Evaluate the model's performance on the validation dataset.
Calculate the Signal-to-Noise Ratio (SNR) for the denoised audio using the estimated IBM masks and the noisy spectrograms.
SNR is calculated as: SNR = 10 * log10(Σ(s^2) / Σ(e^2)), where "s" is the clean speech and "e" is the estimated noise.

### Results
Assess the performance of the trained RNN by examining the validation loss and the SNR values of the denoised audio.

### Conclusion
This project demonstrates the use of RNNs for speech denoising using Ideal Binary Masks. By training an RNN to predict these masks, I was able to effectively separate speech from noise in audio signals, resulting in improved signal quality.With very simple RNN using 2 LSTM layers, 1 dense layer and dropout, I achieved SNR of 12.36 dB on validation data.

### Future Work
In future work, you can explore the following:

Model Architecture: Experiment with more sophisticated RNN architectures, such as GRU, and investigate the impact on denoising performance.
Real-time Denoising: Optimize the model for real-time speech denoising applications.
Transfer Learning: Consider using pre-trained models or transfer learning on larger datasets to improve performance.
Hyperparameter Tuning: Fine-tune hyperparameters to achieve better SNR results.
