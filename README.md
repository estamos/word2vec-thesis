<h1 align="center">
  <a href="https://uth.gr" title="University of Thessaly">
    <img alt="University of Thessaly" src="https://www.uth.gr/sites/default/files/contents/logos/UTH-logo-english.png" width="200px" height="200px" />
  </a>
  <br />
  word2vec-thesis
  <p align="center">
   <a href="https://ir.lib.uth.gr/xmlui/handle/11615/57704">
    <img alt="Thesis as published in UTH Institutional Repository" src="https://img.shields.io/badge/Thesis- as published in Institutional Repository-red.svg" />
  </a>

</p>
  <p align="center">
   <a href="https://github.com/estamos/word2vec-thesis/files/7202631/Stamos_Evangelos_Thesis.pdf">
    <img alt="Thesis" src="https://img.shields.io/badge/Thesis-PDF-white.svg" />
  </a>
  <a href="https://github.com/estamos/word2vec-thesis/files/7216144/Stamos_Evangelos_Thesis_Presentation.pdf">
    <img alt="Thesis Presentation" src="https://img.shields.io/badge/Thesis_Presentation-PDF-lightgrey.svg" />
  </a>
</p>
</h1>
Developed as a part of thesis "Big Data Analytics using Machine Learning Algorithms" - A Word2vec comparative study of CBOW and Skipgram.

<p align="center">
   <a href="https://github.com/estamos/word2vec-thesis/releases/download/v1.1.2/dataset.tar.gz">
    <img alt="Dataset" src="https://img.shields.io/badge/Wiki_corpus-Dataset-red.svg" />
  </a>
  <a href="https://github.com/estamos/word2vec-thesis/releases">
    <img alt="Releases" src="https://img.shields.io/github/v/release/estamos/word2vec-thesis" />
  </a>
  <a href="https://github.com/estamos/word2vec-thesis/releases/download/v1.1.2/pre-trained-models.tar.gz">
    <img alt="Pre-trained models" src="https://img.shields.io/badge/Pre_trained-Models-orange.svg" />
  </a>
</p>

## Run
```bash
# Download latest available release
wget https://github.com/estamos/word2vec-thesis/releases/download/final/word2vec-thesis-final.tar.gz
tar -xvf word2vec-thesis-final.tar.gz
cd word2vec-thesis-final
cp test/test.py models
cd models
pip install gensim tabulate
python test.py
```
## Word2vec - CBOW & Skipgram Comparative Tool

<p align='center'>
  <a><img alt="Word2vec - CBOW & Skipgram Comparative Tool" src="https://user-images.githubusercontent.com/23742352/121664534-407e3580-cab0-11eb-9723-bf8ba8a122ac.gif"></a>
</p>


## Word2vec Architectures Performance Comparison Graphs

#### Effective words per epoch
<img alt="Effective words per epoch" src="https://user-images.githubusercontent.com/23742352/133771033-ebb0cc04-18d6-4ce4-8252-c4edac3471d5.png">

#### Training time per epoch
<img alt="Training time per epoch" src="https://user-images.githubusercontent.com/23742352/133771479-81d89382-492a-4e09-ab11-9174a053b892.png">


## Word2vec Parameterization

|**Gensim parameter**|**Tensorflow parameter**|**Type**|**Details**|
|:------------------:|:----------------------:|:------:|:---------:|
| alpha | learning_rate | float | The initial learning rate |
| cbow_mean | - | boolean | 0: use the sum of the context word vectors <br/> 1: use the mean, only applies when cbow is used |
| epochs | epochs | int | Number of iterations (epochs) over the corpus |
| hs | - | boolean | 0: hierarchical softmax will be used for model training <br/> 1: if negative is non-zero, negative sampling will be used |
| min_count  | min_count | int | Maximum distance between the current and predicted word within asentence |
| negative | num_neg_samples | int | how many "noise words" should be drawn |
| sample | subsample | float | The threshold for configuring which higher-frequency words are randomly downsampled |
| sg | - | boolean | 0: CBOW <br/> 1: Skipgram |
| vector_size | embedding_dim | int | Dimensionality of the word vectors |	
| window | window_size | int | Maximum distance between the current and predicted word within a sentence |

## Statistics
Trained with parameters 
|**Gensim parameter**|**Value**|
|:------:|:---------:|
| window | 10 
| min_count | 2
| workers | 10
| total_examples | len(documents)
| epochs | 10
### Total training time

|**CBOW**|**Skipgram**|
|:------:|:----------:|
|956.5|3768.5|

### Total effective words

|**CBOW**|**Skipgram**|
|:------:|:----------:|
|1327456338|1327454735|

### Training time per epoch

|**Epoch**|**CBOW**|**Skipgram**|
|:-------:|:------:|:----------:|
|Average|95.65|376.85|
|1|95.9|338.3|
|2|95.3|340.0|
|3|96.7|339.9|
|4|96.1|448.0|
|5|95.4|339.3|
|6|95.3|339.8|
|7|95.6|339.9|
|8|95.3|599.3|
|9|95.3|342.8|
|10|95.6|341.2|

### Effective words per epoch

|**Epoch**|**CBOW**|**Skipgram**|
|:-------:|:------:|:----------:|
|Average|132745634|132745474|
|1|132750757|132744876|
|2|132744712|132741580|
|3|132743879|132750658|
|4|132748376|132743435|
|5|132747942|132749631|
|6|132746112|132744974|
|7|132744511|132745877|
|8|132742194|132744706|
|9|132740767|132745693|
|10|132747088|132743305|


#### Tree
```
.
├── LICENSE
├── README.md
├── dataset
│   └── wiki_en_corpus.txt
├── logs
│   ├── cbow-log.rtf
│   └── skipgram-log.rtf
├── models
│   ├── word2vec-cbow-trained.model
│   ├── word2vec-cbow-trained.model.syn1neg.npy
│   ├── word2vec-cbow-trained.model.wv.vectors.npy
│   ├── word2vec-skipgram-trained.model
│   ├── word2vec-skipgram-trained.model.syn1neg.npy
│   └── word2vec-skipgram-trained.model.wv.vectors.npy
├── test
│   └── test.py
└── train
    ├── cbow
    │   └── cbow.py
    └── skipgram
        └── skipgram.py
```
