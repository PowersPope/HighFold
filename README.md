# HighFold: accurately predicting structures of cyclic peptides and complexes with head-to-tail and disulfide bridge constraints

HighFold is a novel framework for cyclic peptide structure prediction. Based on head-to-tail and disulfide bridge constraints, a Cyclic Position Offset Encoding Matrix (CycPOEM) is constructed and feed into the AlphaFold model. 

## Advantanges of HighFold

- Cyclic peptide structure prediction for both monomers and complexes.
- Multiple cyclizations such as head-to-tail and disulfide bridges.
- High effectiveness and efficiency.

## Code Hierarchy

```shell
bashCopy highfold/
├── alphafold/          # core codes from alphafold
├── colabfold/          # colabfold implement
├── utils/              # construction of CycPOEM, combination of disufide bridges and metrics
├── LICENSE             # license file
└── README.md           # readme
└── HighFold_data       # HighFold_data is the dataset used in our work.
```

## Instructions

### Installation

You can install the ColabFold by the script LocalColabFold (details on https://github.com/YoshitakaMo/localcolabfold) at first, and then copy the source codes of HighFold into the installed ColabFold project.

As an example, within your localcolabfold directory `<path-to-dir>/localcolabfold/colabfold-conda/lib/python3.10/site-packages/`. You need to delete your `alphafold/` and `colabfold/` directories. Then replace them with the `alphafold/, colabfold/, and utils/` directories from this repo!

### Data Preparation

The amino acid sequence should be processed in fasta format.

```
>fasta
SAKIDNLD:
SSPGIWLDCTHLEGKVILVAVHVASGYIEAVIPAETGQETAYFLLLAGRWPVKTHDNGSNFTSTTVKAACWWAGIQEDGIPYNPQSQGVIESMNKELKKIIGQVRDQAEHLKTAVQMAVFIHNHKRKGYSAGERIVIIATDIQ:
SSPGIWLDCTHLEGKVILVAVHVASGYIEAVIPAETGQETAYFLLLAGRWPVKTHDNGSNFTSTTVKAACWWAGIQEDGIPYNPQSQGVIESMNKELKKIIGQVRDQAEHLKTAVQMAVFIHNHKRKGYSAGERIVIIATDIQ
```

### Structure Prediction

To run the prediction, type

```sh
colabfold_batch --templates --amber --model-type alphafold2 file_input path_output [args]
```

## Citation
```
@article {Zhang2023.08.27.554979,
	author = {Zhang, Chenhao and Zhang, Chengyun and Shang, Tianfeng and Wu, Xinyi and Duan, Hongliang},
	title = {Highfold: accurately predicting cyclic peptide monomers and complexes with AlphaFold},
	elocation-id = {2023.08.27.554979},
	year = {2023},
	doi = {10.1101/2023.08.27.554979},
	publisher = {Cold Spring Harbor Laboratory},
	abstract = {In recent years, cyclic peptides have gained growing traction as a therapeutic modality owing to their diverse biological activities. Understanding the structures of these cyclic peptides and their complexes can provide valuable insights. However, experimental observation needs much time and money, and there still are many limitations to CADD methods. As for DL-based models, the scarcity of training data poses a formidable challenge in predicting cyclic peptides and their complexes. In this work, we present {\textquotedblleft}High-fold,{\textquotedblright} an AlphaFold-based algorithm that addresses this issue. By incorporating pertinent information about head-to-tailed circular and disulfide bridge structures, Highfold reaches the best performance in comparison to other various approaches. This model enables accurate prediction of cyclic peptides and their complexes, making a step to-wards resolving its structure-activity research.Competing Interest StatementThe authors have declared no competing interest.},
	URL = {https://www.biorxiv.org/content/early/2023/08/28/2023.08.27.554979},
	eprint = {https://www.biorxiv.org/content/early/2023/08/28/2023.08.27.554979.full.pdf},
	journal = {bioRxiv}
}
```

## Version History

- v1.1.0 (2024-11-08):

