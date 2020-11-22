# lowresourcecqa

This is a dataset associated with the following publication:

```bibtex
@inproceedings{poerner-schutze-2019-multi,
    title = "Multi-View Domain Adapted Sentence Embeddings for Low-Resource Unsupervised Duplicate Question Detection",
    author = {Poerner, Nina  and Schütze, Hinrich},
    booktitle = "Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing (EMNLP-IJCNLP)",
    month = nov,
    year = "2019",
    address = "Hong Kong, China",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/D19-1173",
    doi = "10.18653/v1/D19-1173",
    pages = "1630--1641"
}
```

## Data
__data/lowresource.zip__

Contains training and test data from 12 low-resource Stack Exchange forums (December 2018 data dump).
The zipfile contains 36 files (3 per forum):

__$FORUM.stackexchange.train.tsv__

Unlabeled questions for representation training. 
Unlabeld questions are all questions that are not flagged as duplicates.
They may or may not be originals of duplicates. The TSV is structured as follows:

* _qid_: question ID from Stack Exchange
* _title_: preprocessed question title
* _body_: preprocessed question body
* _date_: time stamp from Stack Exchange

We concatenate question titles and bodies when training or calculating question representations. 
The time stamp is for reference only, we did not use it in our experiments.

__$FORUM.stackexchange.test.tsv__

All labeled duplicates. Structured like __$FORUM.stackexchange.train.tsv__.

__$FORUM.stackexchange.gt.tsv__

Ground truth question pairs. Structured as follows:

* _qid_: question ID of duplicate. Always from __$FORUM.stackexchange.test.tsv__
* _rqid_: question ID of original. May be from __$FORUM.stackexchange.test.tsv__ or __$FORUM.stackexchange.train.tsv__
