# piano-transcription
Turn audio recordings into piano sheets

This repo contains two notebooks including (i) audio data preprocessing and (ii) the training of a model designed to recognize piano notes. It can be used to turn audio recordings into piano sheets.

**Database**

- Very short midi files with one or many notes played simultaneously (midi files contains information such as as musical notes, timing, velocity, pitch, and instrument data)

**X data pre-processing** (cf. file 1-data-preprocessing.ipynb)

- Each midi (.mid) is converted into audio (.wav) file
- Each audio file (.wav) is converted into a CQT spectrogram (.png)
- Each spectrogram (.png) is converted into a grey-scale 1d array and resized to a unique format (60 x 150)

**y data pre-processing** (cf. file 1-data-preprocessing.ipynb)

- The notes played are extracted from the midi (.mid) files and are one-hot encoded

**Model training** (cf. file 2-model-training.ipynb)

- Convolutional layers were used to extract spatial features from each spectogram
- Sigmoid activation and binary crossentropy loss functions were used to capture multiple notes played simultaneously
- Model accuracy reaches 0.96 on train, val and test sets
