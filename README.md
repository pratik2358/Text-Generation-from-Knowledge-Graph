# Text-Generation-from-Knowledge-Graph
This work is an exploration and understanding of the original work by Rik Koncel-Kedziorski, Dhanush Bekal, Yi Luan, Mirella Lapata, Hannaneh Hajishirzi

# Requirements:
cuda version 10.2
PyTorch 1.6.0
use "pip install torch==1.6.0 torchvision==0.7 torchtext==0.7 allennlp==1.1.0 urllib3==1.25.4 folium==0.2.1" to install these requirements.

# Description:
The dataset used here is called **Abstract GENeration DAtaset** or **AGENDA**, which consists of 40,720 annotated titles and abstracts from Computer Science papers published in different conferences. The annotation is done by SciIE (an information extraction system) by Luan et al.
## Dataset Description:
**column1:** title

**column2:** entities - semi-colon delimited list of entities
**column3:** entity type - space delimited list of one type token associated with each entity (types: METHOD, MATERIAL, TASK, METRIC, OTHERSCIENTIFICTERM)

**column4:** graph - semi-colon delimited list of graph triples, where head and tail are indices of the entities in the 2nd column. The middle one in the triple is a relation from the file relations.vocab

**column5:** target - target text with entities replaced by placeholders indicating the entity type and its index in the 2nd column.

**column6:** ordering (Not used)

# Working:
The model takes the title and a knowledge graph as input and writes the abstract as the output.
The detailed mathematics and procedure is given the the presentation link given : https://docs.google.com/presentation/d/1xS_cOT5ktxZ4NP1uOfzzbgt6VwdfdpJd3WiHyS0L9wM/edit?usp=sharing

# Instructions:
**Training:**
```
python3.6 train.py -save <DIR>
```  
Use --help for a list of all training options.

  
**Generation:**
```
python3.6 generator.py -save <SAVED MODEL>
```  

**Evaluation:**
```
python3.6 eval.py <GENERATED TEXTS> <GOLD TARGETS>
```
  
# Citation
  
```
@inproceedings{koncel2019text,
  title={{T}ext {G}eneration from {K}nowledge {G}raphs with {G}raph {T}ransformers},
  author={Rik Koncel-Kedziorski, Dhanush Bekal, Yi Luan, Mirella Lapata, and Hannaneh Hajishirzi},
  booktitle={NAACL},
  year={2019}
}
```
