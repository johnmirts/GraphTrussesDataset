[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.16544554.svg)](https://doi.org/10.5281/zenodo.16544554)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

## Table of contents
- [Overview](#overview)
- [Contents](#contents)
- [Usage](#usage)
- [Preprocessing](#preprocessing)
- [Related publications](#related-publications)
- [License](#license)
- [Citation](#citation)

## Overview
This is the first public release of the **Graph Structural Truss Dataset**, intended for research in graph machine learning, topological clustering, and structural analysis. The dataset comprises weighted, undirected graphs representing networks of bars under tension and compression, in a state of static equilibrium.

The dataset was generated using a grammar-based design workflow developed by [Dr. sc. Ioannis Mirtsopoulos](https://www.linkedin.com/in/ioannismirtsopoulos/) during his doctoral research at the [Structural Xploration Lab (SXL)](https://www.epfl.ch/labs/sxl/) of École polytechnique fédérale de Lausanne (EPFL), and further refined during his postdoctoral research in the [Digital Structures](http://digitalstructures.mit.edu/) group at the Massachusetts Institute of Technology (MIT).

The design methodology has been implemented as a plugin named [Libra](https://github.com/StructuralXplorationLab/Libra), developed for the parametric modeling environment Grasshopper within Rhinoceros 3D. Dataset generation employed various sampling strategies, with the outputs of each method organized into correspondingly named folders.

## Contents
Each folder contains graphs generated with the sampling method indicated as the folder name.
- `graph.csv`: per-graph properties such as static action, min/max force, and number of nodes
- `edges.csv`: per edge properties such as start/end node id, label etc.
- `nodes.csv`: per node properties such as x,y,z coordinates, label etc.

The structure of these `.csv` files is inspired by [topologicpy](https://pypi.org/project/topologicpy/).

#### Graphs.csv
| DESCRIPTION	| VARIABLE NAME	|
| --- | --- | 
| The graph ID	| graph_id
| The graph label <br>_(0 for planar / 1 for non-planar)_	| label
| The graph features:<br>  _static action [0]; min length [1]; max length [2]; mean length [3]; standard deviation length [4]; min axial force [5]; max axial force [6]; mean axial force [7]; standard deviation axial force [8]_ | feat

#### Edges.csv
| DESCRIPTION	| VARIABLE NAME	|
| --- | --- |
| The graph id it belongs to | graph_id
| The starting node ID	| src_id
| The ending node ID | dst_id
| The edge label<br> _(the edge ID)_	| label
| The edge features:<br> _axial force: tension < 0, compression > 0_ | feat

#### Nodes.csv
| DESCRIPTION	| VARIABLE NAME
| --- | --- |
| The graph ID	| graph_id
| The node ID	| node_id
| The node label<br>_( 0 for "external" / 1 for "internal")_ | label
| The node features:<br> _(valency)_ | feat
| The node X coordinate	| X
| The node Y coordinate	| Y
| The node Z coordinate	| Z

## Usage
Copy the `.csv` files locally to your system and extract the relevant information.

## Preprocessing
All graphs have been cleaned and verified for connectivity, planarity, and zero force members.

## Related publications
- **Mirtsopoulos, I.**, Fivet, C., Mueller, C., 2025. “Integrating constructability constraints into an equilibrium-aware grammar for geenrative structural design”, in: _Structures and Architecture. REstructure Rematerialize REthink REuse_ pp. 901–908. <https://doi.org/10.1201/9781003658641>

- **Mirtsopoulos, I.**, Fivet, C., 2023. “Structural Topology Exploration through Policy-Based Generation of Equilibrium Representations.” _Computer-Aided Design_ 160 (July 1, 2023): 103518. <https://doi.org/10.1016/j.cad.2023.103518>

- **Mirtsopoulos, I.**, Fivet, C., 2022. "Exploration of static equilibrium representations; policies and genetic algorithms", in: _Structures and Architecture A Viable Urban Perspective?_ pp. 1137–1144. <https://doi.org/10.1201/9781003023555-136>

- **Mirtsopoulos, I.**, Fivet, C., 2021. "Grammar-based generation of bar networks in static equilibrium with bounded bar lengths", in: _Proceedings of International Association for Shell and Spatial Structures (IASS) Symposium 2020/21_. 23-27 August, Guilford, UK. <https://doi.org/10.15126/900337>

- **Mirtsopoulos, I.**, Fivet, C., 2020. "Design space exploration through force-based grammar rule". _archiDOCT_ 8, 50–64.

## License
This dataset is licensed under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). Please cite appropriately if used.

## Citation
Please cite the DOI and credit the author.

```@software{johnmirts_2025_16544554,
  author       = {Mirtsopoulos, Ioannis},
  title        = {Graph Structural Truss Dataset},
  month        = july,
  year         = 2025,
  version      = {v2025-07},
  doi          = {10.5281/zenodo.16544554},
  url          = {https://doi.org/10.5281/zenodo.16544554},
}
```
