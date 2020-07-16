# Suggestion-Mining-Lmote
This repository is the implemention of the research paper [A Multi-task Approach to Open Domain Suggestion Mining](https://aaai.org/Papers/AAAI/2020GB/SA-JainM.408.pdf) - Minni Jain, Maitree Leekha∗, Mononito Goswami 

## Results
The training data is obtained from [SemEval 2019 Task 9 - SubTask A](https://competitions.codalab.org/competitions/19955)
The imbalance in the training data is handled using LMOTE and SMOTE techniques.

### Ensemble Classifier
Ensemble Classifier consists of:
1. A CNN Classifier
2. A LSTM Classifier with attention
3. A BILSTM based text RCNN classifier

<p align="center"><img src="https://github.com/shubhamk0027/Suggestion-Mining-Lmote/blob/master/Model%20Ensemble_Classifier.png"></p>

### Using LMOTE Technique

F1-Score: 79

Accuracy-Score: 78

A Bilstm based RNN Encoder-Decoder Text Generator model was used for generating the new training samples.
It was trained over the suggestion texts with ngrams (n=5) as input and the next word as the output. 
And for generating new samples, top ngrams from the training data (including the non sugg) texts were used as the seed to the model for suggestion generation.
<p align="center"><img src="https://github.com/shubhamk0027/Suggestion-Mining-Lmote/blob/master/Model%20Lmote%20Sequence%20Generator.png" width=500 ></p>

### Using SMOTE Technique

F1-Score: 78

Accuracy-Score: 80

### Conclusion

Using LMOTE technique for data imbalance, results are slightly better than the SMOTE technique.
