# OntoClue

_Ontology-based label assignment supporting literature recommendations_

_A research project by the Semantic Technologies team at [ZB MED](zbmed.de)_

OntoClue is a research project aiming at finding and assigning topics to scholarly publications. It relies on background knowledge provided by ontologies and uses technologies such as graph embeddings, ontology hierarchical partition and name entity recognition.

## Motivation
* Scholarly publications remain the main research object used to disseminate research findings
* Navigation and selection of relevant publications remain a challenge
  * Recommended/Similar articles are (mostly) based on title and abstract elements and (mostly) based on similarity rather than relatedness
  * Ontology-based recommendations are a step further but still rely mostly on similarity
  * We are still missing serendipity
    * Different yet relevant/related articles
    * Possibly targeting different sections on full papers

## Our idea
Using ontology term clusters together with name entity recognition to find relevant (but not necessarily highly similar) scholarly articles and tailor recommendations to a specific section of the article (only for full text).

## Phases
Ontoclue comprises three main phases:
* Phase 1: Ontology-based clustering
* Phase 2: Recommender system
* Phase 3: Integration to Livivo ZB MED literature search portal

### Current status and projects
We are curretly exploring ways to cluster ontology terms so clusters can be later combined with semantically annotated literature in order to find relevant articles to a reference one.

* Clustering of ontology terms with OWL2Vec*: We first create ontology embeddings with [OWL2Vec*](http://arxiv.org/abs/2009.14654) and then we create clusters out of the embeddings. We are currently exploring the sort of clusters we can obtain (from broad large clusters to fine-grained ones) and analizing the possibilities brought by them
* Name entity recognition (NER): We are using [Whatizit](https://academic.oup.com/bioinformatics/article/24/2/296/227269), a dictionary-based NER that can be easily configured. As a proof-on-concept, we are generating Gene Ontology annotations for Medline abstracts from 2015 to 2019. We will first analyzed the ontology spectrum covered by the annotations and then we will combined annotation-based clusters with those coming from graph embedding on the previous step

## Team
* Georgi Lazarov, University of Bonn (contributting to developments on name entity recognition)
* Ashley Ritchie, City London University (contributting to developments on ontology-based embeddings and clustering)
* Benjamin Wolff, ZB MED Information Centre for Life Sciences (contributting to developments on tree-based clustering)
* Ernesto Jiménez-Ruiz, City London University (contributting to supervision of ontology-based embeddings and clustering)
* Dietrich Rebholz-Schuhmann, ZB MED Information Centre for Life Sciences (concept and overall supervision)
* Leyla Jael Castro, ZB MED Information Centre for Life Sciences (concept and overall supervision)
