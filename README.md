# lowresourcecqa

This repository is currently under construction.

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
