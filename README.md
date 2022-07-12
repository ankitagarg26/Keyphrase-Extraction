# SemEval 2017 Task 10: Extracting Keyphrases from Scientific Publications


### Introduction ###
The [SemEval 2017 Task 10](https://scienceie.github.io/) deals with automatic extraction of keyphrases from Computer Science, Material Sciences and Physics publications, as well as extracting types of keyphrases and relations between keyphrases. 

In this project, I have implemented a Bi-LSTM + CRF model to do an end-to-end classification and recognition of keywords. 

### Data ###
SemEval 2017 ScienceIE corpus consists of 500 journal articles evenly distributed among the domains Computer Science, Material Sciences and Physics. The corpus consists of 350 documents for training, 50 for development and 100 for testing. The keywords are classified into three categories: TASK, PROCESS and MATERIAL. 

### Approach ###
### Data Preprocessing ####

1. Text data corresponding to each article in the corpus is processed to get a list of tokens and their corresponding POS tagging using spaCy python library.
2. Before passing the input through the model, the lists are converted into integer sequences, and the resulting sequences are padded to ensure that all sequences are the same length.
3. For each type of keyword, the IOB label scheme is used to generate the output label sequence. The below image shows an example of using the IOB label scheme.

![image](https://user-images.githubusercontent.com/79797476/178479582-4ac65dbd-4cbe-46d0-89d5-3150a55233cb.png)

### Modelling ###

