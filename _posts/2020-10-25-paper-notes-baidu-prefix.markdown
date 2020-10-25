---
layout: post
title:  "Paper Notes:  Personalized Prefix Embedding for POI Auto-Completion in the Search Engine of Baidu Maps"
date:   2020-10-25
categories: [Process, Paper-Notes]
---
***Paper Notes**:  Beginning with this post, I've decided to read one paper every two weeks and post my notes here as a concrete deliverable.  This is part of a habit I'd like to cultivate to read more books, academic papers, and industry blogs.*

## Summary
**The paper:** [KDD2020 - Personalized Prefix Embedding for POI Auto-Completion in the Search Engine of Baidu Maps](https://www.kdd.org/kdd2020/accepted-papers/view/personalized-prefix-embedding-for-poi-auto-completion-in-the-search-engine-)

The paper describes how Baidu Maps improved upon their GBRank-based baseline ranker for POI autosuggest by combining (Q) biLSTM personalized query prefix embeddings with (P) POI attribute embeddings and applying (T) triplet loss training. 


### Q: BiLSTM personalization features
* Let prefix $$p = (c_1, c_2, …, c_n)$$ be the search input as a character sequence, e.g. “baid” = `(‘b', ‘a', ‘i', ‘d’)`.  Encode each character $$c_i$$ as an embedding $$\bm{c_i}$$ from a vocabulary of ~8K Chinese characters, 10 Arabic numbers, and 52 English letters (`[a-zA-Z]`, presumably).
* For a given user $$u$$, learn an embedding $$\bm{u}$$ and append to each character embedding ($$\bm{c_i} \oplus \bm{u}$$).
* Feed the resulting $$n$$ vectors sequentially into a biLSTM network and concatenate the forward and backward states to get $$s_i \in \Reals^d$$.
* Apply attention with `tanh` activation to get $$n$$ scalars $$a_i$$.
* Perform a weighted sum to get the final personalized prefix embedding $$\sum_{i} a_i s_i = e_{u.p.} \in \Reals^l$$[^1].


### P: POI attribute embeddings
For each POI in the result list:
* Use character embeddings with CNN architecture (SenCNN) to map POI name and address to $$\bm{v_{name}} \in \Reals^m$$ and $$\bm{v_{addr}} \in \Reals^m$$.
* Encode one-hot POI categories (~40) into $$\bm{v_{cate}} \in \Reals^m$$ embeddings.
* Encode POI geohashed GPS coordinates into $$\bm{v_{GPS}} \in \Reals^m$$
* Sum up the POI vectors to get $$\bm{v_{POI}} \in \Reals^m$$, use a fully-connected layer to resize to $$\Reals^l$$, and apply sigmoid activation to get $$e_{poi} \in \Reals^l$$

### T: Triplet loss training
Given $$e_{u.p.}$$ (Q) and $$e_{poi}$$ (P) both in $$\Reals^l$$, the authors use the cosine similarity (`cosine(Q, P)`) between the two vectors as the model output.

Training examples are built from historical user click behavior; for a given query prefix $$p$$ with response POIs $$R$$, the clicked POI is assumed to be the correct answer and the other POIs in $$R$$ are assumed to be incorrect answers.  The authors use triplet loss, which aims to simultaneously minimize the distance between the correct answer and maximize the distance from the incorrect answers.  The negative examples are downsampled from $$R$$.

### Results
The basic baseline model is "$$PAC$$ (V1.x)".  This uses time/space/demographic popularity features to re-rank POIs from the candidate retrieval step.

The improved baseline model to beat is "$$P^{2}AC$$ v2.1", which, in addition to the basic features, learns POI embeddings in order to account for the similarity between candidate POIs and a user's historical POIs.  According to the authors, these embeddings are learned in a manner similar to Word2Vec.  My guess is that this means taking user POI usage sequences as the context for applying CBOW or skip-gram prediction, though there are definitely other definitions which would be valid.  To generalize to new POIs, the baseline apparently used the same POI attribute encoding approach used in this paper.  This model gets NDCG@5=0.66 on the offline test datset.

The model developed in the paper is "$$P^{3}AC$$ (V3.x)".

* V3.0 refers to using `cosine(Q, P)` directly as the ranking score.  It improved the test set NDCG@5 by +0.02, to 0.68.
* V3.1 refers to adding `cosine(Q, P)` as a feature in $$P^{2}AC$$ v2.x, which improved NDCG@5 by another +0.02, to 0.70.

### Thoughts
Because Baidu has a large amount of implicit feedback from historical user queries, learning the Q and P embeddings directly using the labeled queries (rather than performing unsupervised learning on user history) was able to yield improved ranking.  DiDi wrote[^2] about a similar approach to POI search ranking, i.e. learning query and POI embeddings in the same space, but with less emphasis on modeling the prefix input sequence (in particular no use of biLSTM architecture) and more emphasis on learning GPS embeddings.

-----
[^1]: If I read this section correctly it sounded like in their case the dimensions $$d$$ and $$l$$ happened to be equal but a final layer transformation could be used if this is not true.
[^2]: [Zhao, Ji, Dan Peng, Chuhan Wu, Huan Chen, Meiyu Yu, Wanji Zheng, Li Ma, Hua Chai, Jieping Ye, and Xiaohu Qie. 2019. “Incorporating Semantic Similarity with Geographic Correlation for Query-POI Relevance Learning.” Proceedings of the AAAI Conference on Artificial Intelligence. https://doi.org/10.1609/aaai.v33i01.33011270.](https://aaai.org/ojs/index.php/AAAI/article/view/3922)