#SK Query Processing

## Overview
To maximize the advantages of both SPARQL and keyword search, in this project, we introduce a novel paradigm that combines them and propose a hybrid query (called a SPARQL-Keyword (SK) query) that integrates SPARQL and keyword search. To answer SK queries efficiently, we propose a novel integrated query algorithm based on a structural index. We also present a distance-based optimization technique to further improve the efficiency of SK queries evaluation. We test our method in three large real RDF graphs and the experiments demonstrate both the effectiveness and efficiency of our method. You can also find out the details of the project in the paper which is in the root directory.

## Usage
There are only two programs: QueryProcessing.java and CreateIndex.java.
   
###1. CreateIndex.java
This is used to load RDF datasets and build indices for it. 

The datasets should be in RDF triple format. The subject and predicate of each triple should be separated by the space, and the predicate and object of each triple should also be separated by the space.

There are three parameters for this program. The first parameter is the path that will store the indices, the second parameter is the path where the RDF dataset is stored and the third one is the number of pivots.

###2. QueryProcessing.java
This is used to processs the SK queries. 

There are also three parameters for this program. The first parameter is the path that will store the indices, the second parameter is the path where the SK query is stored and the third one is the number of results returned.

The file of the SK query consists of two lines. The first line is keywords, which are separated by the semicolons. The second line is a SPARQL query.


## Evaluation
We have tested on this version on a machine with a 2 Ghz Core 2 Duo processor and 64G RAM memory. All the codes are implemented in Java. We used Berkeley DB 5.0.84 to store the indices, Lucene 2.9.4 to build inverted index for keyword search and Sesame 2.8.0 to parse SPARQL queries. The above jars are provided in the root directory. Furthermore, we use an executable program, named `mine`, to find out frequent patterns. The executable program is in the root directory.You need put this executable program into the root directory of you project and change its permission to run.

In this project, we use three real-world RDF datasets, DBLP, Yago and DBPedia & QALD to test our method.

### DBLP
[DBLP](http://dblp.uni-trier.de/) contains bibliographic information for computer science publications. We define five sample SK queries for DBLP. The queries are provided in the root directory. You can download the dataset [here](https://drive.google.com/file/d/0B0Auz4i0D5FYcGRBRS1BX1QwVGs/view?usp=sharing_eip&invite=CK6X0ZwO&ts=58bc201e).

### Yago
[Yago](http://www.mpi-inf.mpg.de/departments/databases-and-information-systems/research/yago-naga/yago/#c10444) extracts facts from Wikipedia and integrates them with the WordNet thesaurus. We define eight sample SK queries for Yago. The queries are also provided in the root directory. You can download the dataset [here](https://drive.google.com/open?id=0B0Auz4i0D5FYNE1mSTZwU2MxN3M).


### DBPedia & QALD. 
[DBPedia](http://wiki.dbpedia.org/) is an RDF dataset extracted from Wikipedia.
[QALD](http://qald.sebastianwalter.org/index.php?x=publications&q=2) is an evaluation campaign on question answering over linked data. In this project, we only select 10 non-aggregation complex queries from QALD for evaluation. You can download the dataset [here] (https://drive.google.com/open?id=0B0Auz4i0D5FYNE1mSTZwU2MxN3M).

Notice: 

If you encounter any problems, please send emails to me (email address: hnu16pp@hnu.edu.cn).