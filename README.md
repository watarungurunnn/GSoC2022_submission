# GSoC2022_submission

## What was done
1. Searched for previous researches and discussed with the mentors and contributors which graph expression and GNN structure are effective for cell tracking.
1. Implemented preprocessing 3D microscopy videos of C.elegans into centroids graph by devolearn.
1. Refactored inference part of the source codes of: Ben-Haim, T. & Riklin-Raviv, T. Graph Neural Network for Cell Tracking in Microscopy Videos. Preprint at http://arxiv.org/abs/2202.04731 (2022).
1. Fixed bugs of external modules. 

## Details of what was done
### 1. Searched for previous researches and discussed with the mentors and contributors which graph expression and GNN structure are effective for cell tracking.
Our goal has been to capture the features of the cells and simulate development of organisms by GNN.

The main points are:
* Each cell occupies some spaces and the locations of the centroids are decided by interactions between nearby cells.
* These interactions are assumed to be expressed by edges of the graphs, while the centroids of the cells are expressed by nodes.

### 2. Implemented preprocessing 3D microscopy videos of C.elegans into centroids graph by devolearn.
- The commits are listed [here](https://github.com/DevoLearn/devolearn/pull/74). [screenshots](https://github.com/watarungurunnn/GSoC2022_submission/blob/main/Screen%20Shot%202022-09-12%20at%2011.41.52.png)

https://github.com/LspongebobJH/DevoGraph/commit/eac3368a6d9d4e982b2583cd6a1b23bbcc641f3d
