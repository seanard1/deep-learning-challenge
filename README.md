# deep-learning-challenge
Module 21 Challenge -- Deep Learning

## Introduction/Premise

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization.

## Modules

sklearn

pandas

tensorflow

keras-tuner

Notebooks built and executed on Google Colab: https://colab.google/

WARNING: Keras Tuner takes approximately 30 minutes to run on this dataset on Google Colab.

## Summary

The Jupyter Notebooks (created and exported from Google Colab) contain the code to clean, split, scale and train nerual network models for the dataset of funding applicants to Alphabet Soup (https://static.bc-edx.com/data/dl-1-2/m21/lms/starter/charity_data.csv). 

Contained in the `AlphabetSoup_Step1_2` notebook is the code for an initial analysis and cleaning of the data, as well as an initial attempt at a neural network. The notebook `AlphabetSoup_Step3`then attempts to optimize this code using additional data cleaning and Keras Tuner analysis to improve the accuracy (spolier: it does not). 

The models are saved in the `Model_Files` directory in this repository.

## Citations

https://stackoverflow.com/questions/50447222/google-colaboratory-keras-save-model-in-hdf5-file-format-and-download-it-to-l

This was used to learn about the export from Google Colab