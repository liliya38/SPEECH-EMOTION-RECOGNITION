# SPEECH-EMOTION-RECOGNITION
## Introduction
Speech Emotion Recognition (SER) is the process of trying to recognise human emotion and effective states from speech. Speech emotion recognition is a very interesting yet very challenging task of human computer interaction. In recent years this topic has grabbed so much attention. In the field of speech emotion recognition many techniques have been utilized to extract emotions from signals, including many wellestablished speech analysis and classification techniques. In the traditional way of speech emotion recognition features are extracted from the speech signals and then the features are selected which is collectively known as a selection module and then the emotions are recognized. This is a very lengthy and time taking process so this project gives an overview of the machine learning technique which is based on a simple algorithm based on feature extraction and model creation which recognizes the emotion.
## Objective
The aim of the project is about the detection of the emotions elicited by the speaker while talking. As an example, speech produced in a state of fear, anger, or joy becomes loud and fast, with a higher and wider range in pitch, whereas emotions such as sadness or tiredness generate slow and low-pitched speech. Detection of human emotions through voicepattern and speech-pattern analysis has many applications such as better assisting human-machine interactions. To recognize emotions based on speech i.e., the audio files, Input will be the audio files and the output will be different kinds of emotions. Based on the voice modulation, pitch and other audio attributes, we are going to classify which emotion it conducts.
## Scope
Emotions play an extremely important role in human mental life. It is a medium of expression of one's perspective or one's mental state to others. Speech Emotion Recognition (SER) can be defined as extraction of the emotional state of the speaker from his or her speech signal.                                                  
### WHY DO WE NEED IT?                                                                                                                                                
1. Emotion recognition is the part of speech recognition which is gaining more popularity and need for it increases enormously. This project attempts to use machine learning to recognize the emotions from data.                                                                                                                          
2. SER(Speech Emotion Recognition) is used in call centre for classifying calls according to emotions and can be used as the performance parameter for conversational analysis thus identifying the unsatisfied customer, customer satisfaction and so on.. for helping companies improving their services                                   
3. It can also be used in-car board systems based on information of the mental state of the driver can be provided to the system to initiate his/her safety preventing accidents from happening.
## About the dataset
The data set is extracted from Kaggle and the name of the data set is Toronto emotional speech set(TESS). There are a set of 200 target words were spoken in the carrier phrase "Say the word _' by two actresses (aged 26 and 64 years) and recordings were made of the set portraying each of seven emotions (anger, disgust, fear, happiness, pleasant surprise, sadness, and neutral). There are 2800 data points (audio files) in total. The dataset is organized such that each of the two female actors and their emotions are contained within its own folder. And within that, all 200 target words audio files can be found. The format of the audio file is a WAV format.
https://www.kaggle.com/datasets/ejlok1/toronto-emotional-speech-set-tess
## Methodology
### Data Collection
• We have collected the data from Kaggle.
• The data that we got is in audio format. So, there was no need for
cleaning.
### Data Augmentation
• Data augmentation is the process by which we create new
synthetic data samples by adding small perturbations on our initial
training set.
• To generate syntactic data for audio, we can apply noise injection,
shifting time, changing pitch and stretch.
• The objective is to make our model invariant to those perturbations
and enhance its ability to generalize.
• In order for this to do this work, adding the perturbations must
conserve the same label as the original training sample.
### Data Exploration
• We have plotted Countplot to recognize the count of emotions.
![image](https://user-images.githubusercontent.com/93417422/185061597-07888b19-dd80-464b-86e3-d8f6024cce89.png)

We have also plotted Wave Plots and Spectrograms for audio signals.
![image](https://user-images.githubusercontent.com/93417422/185061906-d364eacf-640b-4e6d-89f1-aae7ccf69df5.png)

The above figure represents fear emotion. Some pitch and frequency differences can be observed from here. Similarly, we can find waveplots and spectrograms of other emotions as well.
• Waveplots - Waveplots let us know the loudness of the audio at a given time.
• Spectrograms - A spectrogram is a visual representation of the spectrum of frequencies of sound or other signals as they vary with time. It’s a representation of frequencies changing with respect to time for given audio/music signals.
### Feature Extraction
Extraction of features is a very important part in analysing and finding
relations between different things. As we already know that the data
provided of audio cannot be understood by the models directly so we
need to convert them into an understandable format for which feature
extraction is used.
The audio signal is a three-dimensional signal in which three axes
represent time, amplitude and frequency.
![image](https://user-images.githubusercontent.com/93417422/185062349-5004cba7-2b16-4bae-a468-e386fc5cb9fb.png)

With the help of the sample rate and the sample data, one can perform
several transformations on it to extract valuable features out of it. Here
we have done the following feature extractions: -
1. Mean Zero (Zero crossing rate) - The rate of sign-changes of the
signal during the duration of a particular frame.
2. Chroma stft - The Chroma value of an audio basically represents
the intensity of the twelve distinctive pitch classes that are used to
study music. They can be employed in the differentiation of the
pitch class profiles between audio signals.
3. MFCC - MFCCs Mel Frequency Cepstral Coefficients form a
cepstral representation where the frequency bands are not linear
but distributed according to the mel-scale.
4. RMS - It is the root mean square value.
5. MEL Spectrogram - It is a spectogram where the frequencies are
converted to MEL scale.
### Data Processing
• After extracting the features we have normalized the data.
• Then we have split our data for training and testing.
### Evidence of Activity: Modeling
Based on the features that we have extracted, we are going to classify
the emotions by modeling. We have done CONV1D model which is a
machine learning technique. The convolutional layer learns local
patterns of data in convolutional neural networks. It helps to extract the
features of input data to provide the output. CONV1D is used when you
slide your convolution kernels along 1 dimension (i.e. you reuse the
same weights, sliding them along 1 dimensions). It is a sequential
modeling.
The graph below represents the loss, accuracy, validation loss and
validation accuracy of the model.
![image](https://user-images.githubusercontent.com/93417422/185062738-3783d8c6-8236-47b2-b2e4-f17f47173b53.png)

## Conclusion
We have achieved the main objective of the project that is to identify
emotion of a person using convolutional neural networks with Conv1D
model. The feature used in this model is MFCC, chroma_stft, mean zero
and is extracted using librosa package. The extracted values are given
as input to developed Conv1D model which uses these features and
give the final predicted emotion. The overall accuracy obtained in this
model is 98.8%. Furthermore, the accuracy of model can be improved
by clearing random silence from audio clip and adding more data volume
by finding more annotated audio clips.
## Future enhancement
It can be used to develop equipment to help disabled people. This model can be
used by various apps and online websites so that they can know the users
emotions and incorporate new techniques to improve user experience to gain
profits. This system can also be used in call-canters for complaints and also in
voice based virtual assistants or chat box.
In future, we can try implementing this in different modelling techniques and
compare the results. We can also model with different datasets like Ravdees,
Savee, Crema-D datasets.

