# Seyffarth and Kallmeyer (2020): Corpus-based Identification of Verbs Participating in Verb Alternations Using Classification and Manual Annotation (to appear at COLING 2020)

This repository contains data used in the COLING 2020 paper by Esther Seyffarth and Laura Kallmeyer, Corpus-based Identification of Verbs Participating in Verb Alternations Using Classification and Manual Annotation (pdf link and bibtex citation to follow). The files presented here are described in detail in Section 2.1 of the paper.

## Abstract
English verb alternations allow participating verbs to appear in a set of syntactically different constructions whose associated semantic frames are systematically related. 
We use ENCOW and VerbNet data to train classifiers to predict the instrument subject alternation and the causative-inchoative alternation, relying on count-based and vector-based features as well as perplexity-based language model features, which are intended to reflect each alternation's felicity by simulating it. 
Beyond the prediction task, we use the classifier results as a source for a manual annotation step in order to identify new, unseen instances of each alternation. This is possible because existing alternation datasets contain positive, but no negative instances and are not comprehensive. Over several sequences of classification-annotation steps, we iteratively extend our sets of alternating verbs. 
Our hybrid approach to the identification of new alternating verbs reduces the required annotation effort by only presenting annotators with the highest-scoring candidates from the previous classification. Due to the success of semi-supervised and unsupervised features, our approach can easily be transferred to further alternations.

## Sources for our classifier features
We use count-based, vector-based and perplexity-based features. Count-based features are directly derived from frequency observations in the relevant corpora. Vector-based features are based on 300-dimensional Google News vectors, created with word2vec, available here: https://code.google.com/archive/p/word2vec/ Perplexity-based features are based on perplexity scores determined for original sentences and generated alternate sentences, scored with the system available here: https://github.com/kimiyoung/transformer-xl

## ENCOW sentences
The experiments conducted here are based on a subset of sentences from the ENCOW16AX corpus. Included in this repository are only sentence IDs; go to https://corporafromtheweb.org/encow16/ to learn how to access ENCOW and extract the relevant sentences, based on their IDs.


## `cia`
Contains our corpus and verb set data for the causative-inchoative alternation. `cia_ids.json` is a json file containing all ENCOW sentence IDs we used for this task, separated into "intransitive" and "transitive".

The text files contain
- the positive verbs sourced from VerbNet that were attested in each corpus version (full/reduced),
- and the negative sets we generated based on corpus statistics, such that each positive verb is complemented with a negative verb of the same frequency (summed over all subcorpora for the task).

## `isa`
Contains our corpus and verb set data for the instrument subject alternation. `isa_ids.json` is a json file containing all ENCOW sentence IDs we used for this task, separated into "with", "using" and "subject".

The text files contain
- the positive verbs sourced from VerbNet that were attested in each corpus version (full/reduced),
- and the negative sets we generated based on corpus statistics, such that each positive verb is complemented with a negative verb of the same frequency (summed over all subcorpora for the task).

