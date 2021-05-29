# ARC-Sim
This repository contains a link to and description of the ARC-Sim dataset from our paper _Recovering Lexically and Semantically Reused Texts_, published at *SEM-21.

# Dataset: Information & Copyright
This dataset is derived from the [ACL Anthology Reference Corpus (ARC)](https://www.aclweb.org/anthology/L08-1005/). Please see that paper for more details about the original corpus, and our paper for the processing and filtering steps we took. The data in ARC is from the ACL Anthology and is licensed under a [Creative Commons 3.0 BY-NC-SA](https://creativecommons.org/licenses/by-nc-sa/3.0/) license. Thus, this data is also distributed under the same [Creative Commons 3.0 BY-NC-SA](https://creativecommons.org/licenses/by-nc-sa/3.0/) license as the original. Please see the [ACL Anthology copyright page](https://www.aclweb.org/anthology/faq/copyright/) for full details.

# Dataset: Files & Format
The dataset contains three files: train.jsonl.zip, val.jsonl.zip, test.jsonl.zip. Each is a compressed jsonlines file, with one json record per line. 

Each record contains the following fields:
- cited_paper_id: string, the ACL Anthology ID of the source paper, e.g. [P08-1119](https://www.aclweb.org/anthology/P08-1119/)
- cited_paper_abstract: List[str], the abstract of the source paper, broken up into sentences. One list item per sentence. 
- citing_paper_id: string, the ACL Anthology ID of the target paper, e.g. [P10-1044](https://www.aclweb.org/anthology/P10-1044/). Note, as described in the paper, we only use a single section from each target paper as the target documents for each pair.
- doc_label: int, 0 or 1, indicating whether the target paper section cites the source paper. 
- sentence_labels: List[int], each int is either 0 or 1. Labels for each of the sentences in the target paper section indicating whether they contain a citation to the source paper.
- citing_paper_section_text: List[str], list of sentences in the target paper section. This list has the same length as sentence_labels. All citation marks have been removed from the text. 

# Citation
If you use our dataset, please cite our paper:
Ansel MacLaughlin*, Shaobin Xu*, and David A Smith. Recovering Lexically and Semantically Reused Texts. In _Proceedings of the Tenth Joint Conference on Lexical and Computational Semantics_ (\*SEM-21), 2021
