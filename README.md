# Semantic Relations between Wikipedia Articles

<a href="https://colab.research.google.com/github/malteos/semantic-document-relations/blob/master/demo-wikidocrel.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Implementation, trained models and result data for the paper. 
The supplemental material is available for download under [GitHub Releases](https://github.com/malteos/semantic-document-relations/releases).

## Getting started

**Requirements:**
- Python >= 3.7 (Conda)
- Jupyter notebook (for evaluation)
- GPU with CUDA-support (for training Transformer models)

At first we advise to create a new virtual environment for Python 3.7 with Conda:
```bash
conda create -n docrel python=3.7
conda activate docrel
```

Install all Python dependencies:
```bash
pip install -r requirements.txt
```

Download dataset (and pretrained models):

```bash
# Navigate to data directory
cd data

# Wikipedia corpus
wget https://github.com/malteos/semantic-document-relations/releases/download/1.0/enwiki-20191101-pages-articles.weighted.10k.jsonl.bz2
bzip2 enwiki-20191101-pages-articles.weighted.10k.jsonl.bz2

# Train and test data
wget https://github.com/malteos/semantic-document-relations/releases/download/1.0/train_testdata__4folds.tar.gz
tar -xzf train_testdata__4folds.tar.gz

# Models
wget https://github.com/malteos/semantic-document-relations/releases/download/1.0/model_wiki.bert_base__joint__seq512.tar.gz
tar -xzf model_wiki.bert_base__joint__seq512.tar.gz
```


## Experiments 


Run predefined experiment (settings can be found in `experiments/predefined/wiki`)
```bash
# Config: wiki.bert_base__joint__seq128
# GPU ID: 1 (set via CUDA_VISIBLE_DEVICES=1)
# Output dir: ./output
python cli.py run ./output 1 wiki.bert_base__joint__seq512
```


## Demo

You can run a Jupyter notebook on Google Colab:

<a href="https://colab.research.google.com/github/malteos/semantic-document-relations/blob/master/demo-wikidocrel.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>


## License

MIT