# Kazakh Named Entity Recognition
This repository contains an open-source Kazakh named entity recognition dataset (KazNERD), named entity annotation guidelines (in Kazakh), and NER model training codes (CRF, BiLSTM-CNN-CRF, BERT and XLM-RoBERTa).
- [KazNERD Corpus](#KazNerd)
- [Annotation Guideline](#guide)
- [NER Models](#models)
- [Citation](#cite)

## KazNERD Corpus <a name="KazNerd"></a>
KazNERD contains 112,702 sentences, extracted from the television news text, and 136,333 annotations for 25 entity classes.
All sentences in the dataset were manually annotated by two native Kazakh-speaking linguists, supervised by ISSAI's scientist.
The IOB2 scheme was used for annotation.
The dataset, in CoNLL 2002 format, is located [here](KazNERD).


## Annotation Guideline <a name="guide"></a>
The annotation guideline for 25 named entity classes is located here.
The guideline is written in Kazakh language.


## NER Models <a name="models"></a>
### Setup Conda Environment
The NER training codes are based on **PyTorch 1.7.1** and **Python 3.8**.
To ease the experiment replication experience, we recommend to setup **Conda** environment. 

Create conda environment and install dependencies as follows:
```
$ conda create --name <env> --file requirements.txt
```
where `<env>` will be used as a name of created conda environment, replace `<env>` with any string (e.g., *kaznerd*).
  
  
### CRF 
#### Setup Conda Environment for CRF
The CRF-based NER model training codes are based on **Python 3.8**.
To ease the experiment replication experience, we recommend to setup **Conda** environment. 
```bash
conda create --name knerdCRF python=3.8
conda install -c anaconda nltk scikit-learn
conda install -c conda-forge sklearn-crfsuite seqeval
```

#### Start CRF training
```bash
$ cd crf
$ python runCRF_KazNERD.py
```


### BiLSTM-CNN-CRF
#### Setup Conda Environment for BiLSTM-CNN-CRF
The BiLSTM-CNN-CRF-based NER model training codes are based on **Python 3.8** and **PyTorch 1.7.1**.
To ease the experiment replication experience, we recommend to setup **Conda** environment. 
```bash
conda create --name knerdLSTM python=3.8
# Check https://pytorch.org/get-started/previous-versions/#v171
# to install a PyTorch version suitable for your OS and CUDA
# or feel free to adapt the code to newer PyTorch version
conda install pytorch==1.7.1 torchvision==0.8.2 torchaudio==0.7.2 cudatoolkit=10.1 -c pytorch # we used this version
conda install -c conda-forge tqdm seqeval
```

#### Start BiLSTM-CNN-CRF training
```bash
$ cd BiLSTM_CNN_CRF
$ bash run_train_p.sh
```

## BERT and RoBERTa
#### Setup Conda Environment for BERT and RoBERTa
The BERT- and RoBERTa-based NER models training codes are based on **Python 3.8** and **PyTorch 1.7.1**.
To ease the experiment replication experience, we recommend to setup **Conda** environment. 
```bash
conda create --name knerdBERT python=3.8
# Check https://pytorch.org/get-started/previous-versions/#v171
# to install a PyTorch version suitable for your OS and CUDA
# or feel free to adapt the code to newer PyTorch version
conda install pytorch==1.7.1 torchvision==0.8.2 torchaudio==0.7.2 cudatoolkit=10.1 -c pytorch # we used this version
conda install -c anaconda numpy
conda install -c conda-forge seqeval
conda install -c huggingface transformers
```

#### Start BERT training
```bash
$ cd bert
$ python run_finetune_kaznerd.py bert
```

### Start XLM-RoBERTa training
```bash
$ cd bert
$ python run_finetune_kaznerd.py roberta
```

## Citation <a name="cite"></a>

```bibtex
@inproceedings{
}
```
