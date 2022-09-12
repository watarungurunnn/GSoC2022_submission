# GSoC2022_submission

## What was done
1. Searched for previous researches and discussed with the mentors and contributors which graph expression and GNN structure are effective for cell tracking.
2. Refactored inference part of the source codes of: Ben-Haim, T. & Riklin-Raviv, T. Graph Neural Network for Cell Tracking in Microscopy Videos. Preprint at http://arxiv.org/abs/2202.04731 (2022).
3. Implemented preprocessing 3D microscopy videos of C.elegans into centroids graph by devolearn.
4. Fixed bugs of external modules. 

## Details of what was done
### 1. Searched for previous researches and discussed with the mentors and contributors which graph expression and GNN structure are effective for cell tracking.
Our goal has been to capture the features of the cells and simulate development of organisms by GNN.

The main points are:
* Each cell occupies some spaces and the locations of the centroids are decided by interactions between nearby cells.
* These interactions are assumed to be expressed by edges of the graphs, while the centroids of the cells are expressed by nodes.

### 2. Refactored inference part of the source codes of: Ben-Haim, T. & Riklin-Raviv, T. Graph Neural Network for Cell Tracking in Microscopy Videos. Preprint at http://arxiv.org/abs/2202.04731 (2022).


### 3. Implemented preprocessing 3D microscopy videos of C.elegans into centroids graph by devolearn.
- The commits are listed [here](https://github.com/DevoLearn/devolearn/pull/74).   (-> [screenshot](https://github.com/watarungurunnn/GSoC2022_submission/blob/main/Screen%20Shot%202022-09-12%20at%2011.45.27.png))

https://github.com/LspongebobJH/DevoGraph/commit/eac3368a6d9d4e982b2583cd6a1b23bbcc641f3d

### 4. Fixed bugs of external modules. 
- Installed package from the pip could not used as written in README.md, so added instruction to install from the source. [PR under review](https://github.com/DevoLearn/devolearn/pull/73)
- Fixed wrong URL of the provided trained model. [PR merged](https://github.com/DevoLearn/devolearn/pull/67)
- Fixed regionprops of scikit-image to consider negative value very close to 0 to be 0. [Folk](https://github.com/scikit-image/scikit-image/commit/dede59c19817bceccf80de8eb59eb29db746e1c5)
  - This change was needed to run the cell-tracking-gnn on 3D datasets.
