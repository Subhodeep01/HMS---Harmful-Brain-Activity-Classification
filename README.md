# HMS---Harmful-Brain-Activity-Classification
The goal of this competition is to detect and classify seizures and other types of harmful brain activity. The classification categories include seizures (SZ), generalized periodic discharges (GPD), lateralized periodic discharges (LPD), lateralized rhythmic delta activity (LRDA), generalized rhythmic delta activity (GRDA), or "other".

## Overview
This is a project hosted on Kaggle, employing machine learning techniques to analyze EEG and spectrogram data to classify various harmful brain activities. The project focuses on aiding medical professionals in diagnosing and understanding neurological disorders more effectively.

## Dataset
The dataset is available at Kaggle and can be downloaded using the following command: kaggle competitions download -c hms-harmful-brain-activity-classification(Link to Kaggle api documentation and usage - https://github.com/Kaggle/kaggle-api)<br/>
The dataset comprises EEG and spectrogram readings collected over time from patients exhibiting harmful brain activities. 

**train.csv** Metadata for the train set. The expert annotators reviewed 50 second long EEG samples plus matched spectrograms covering 10 a minute window centered at the same time and labeled the central 10 seconds. Many of these samples overlapped and have been consolidated. train.csv provides the metadata that allows you to extract the original subsets that the raters annotated.

**eeg_id** - A unique identifier for the entire EEG recording.<br/>
**eeg_sub_id** - An ID for the specific 50 second long subsample this row's labels apply to.<br/>
**eeg_label_offset_seconds** - The time between the beginning of the consolidated EEG and this subsample.<br/>
**spectrogram_id** - A unique identifier for the entire EEG recording.<br/>
**spectrogram_sub_id** - An ID for the specific 10 minute subsample this row's labels apply to.<br/>
**spectogram_label_offset_seconds** - The time between the beginning of the consolidated spectrogram and this subsample.<br/>
**label_id** - An ID for this set of labels.<br/>
**patient_id** - An ID for the patient who donated the data.<br/>
**expert_consensus** - The consensus annotator label. Provided for convenience only.<br/>
**[seizure/lpd/gpd/lrda/grda/other]_vote** - The count of annotator votes for a given brain activity class. The full names of the activity classes are as follows: lpd: lateralized periodic discharges, gpd: generalized periodic discharges, lrd: lateralized rhythmic delta activity, and grda: generalized rhythmic delta activity . A detailed explanations of these patterns is available here.

**test.csv** Metadata for the test set. As there are no overlapping samples in the test set, many columns in the train metadata don't apply.

eeg_id<br/>
spectrogram_id<br/>
patient_id<br/>

## Methodology
The project utilizes a combination of signal processing techniques, feature extraction, and machine learning algorithms for classification. Key steps in the methodology include:

**Preprocessing**: Cleaning and preparing the EEG and spectrogram data for analysis, including noise reduction and normalization.<br/>
**Feature Extraction**: Identifying relevant features from the data that characterize different types of harmful brain activities.<br/>
**Model Training**: Vector embeddings were created for the data before feeding into the model. Utilizing various machine learning algorithms such as LSTM(Long Short-Term Memory) and MLP(Multilayer Perceptron).<br/>
**Model Evaluation**: Assessing the performance of trained model using Kullback Liebler divergence between the predicted probability and the observed target.<br/>
**Submission**: For each eeg_id in the test set, predict a probability for each of the vote columns. <br/>

### Link to Kaggle notebook: 
https://www.kaggle.com/code/subhodeepghosh01/3lancers-neural-net/notebook
