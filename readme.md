Hello!

Below you can find a outline of how to reproduce my solution for the <Competition Name> competition.
If you run into any trouble with the setup/code or have any questions please contact me at <email>

#ARCHIVE CONTENTS
models          : trained models
predictions                     : models predictions
data                     : data for training and preprocessed data (contains preprocessed data already for fast predictions)


#HARDWARE: (The following specs were used to create the original solution)
Ubuntu 16.04 LTS (512 GB boot disk)
n1-standard-16 (16 vCPUs, 60 GB memory)

#SOFTWARE (python packages are detailed separately in `requirements.txt`):
Python 3.5.1

#DATA SETUP (assumes the [Kaggle API](https://github.com/Kaggle/kaggle-api) is installed)
# below are the shell commands used in each step, as run from the top level directory

cd data
kaggle competitions download -c competitive-data-science-predict-future-sales
unzip competitive-data-science-predict-future-sales.zip

#DATA PROCESSING
# The train/predict code will also call this script if it has not already been run on the relevant data.
python ./preprocessing.ipynb

#MODEL BUILD: There are three options to produce the solution.
1) train and predict
    a) preprocess data
    b) train models
    c) predict
2)  prediction
    a) predict on preprocessed data and trained models

shell command to run each build is below
#1) train and predict (overwrites predictions and models and data.pkl in data directory)
python ./train.ipynb

#2) predict (overwrites predictions in predictions directory)
sh ./predict.ipynb
