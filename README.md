# GSoC2022_submission

## What was done
1. Searched for previous researches and discussed with the mentors and contributors which graph expression and GNN structure are effective for cell tracking.
2. Refactored inference part of the source codes of: Ben-Haim, T. & Riklin-Raviv, T. Graph Neural Network for Cell Tracking in Microscopy Videos. Preprint at http://arxiv.org/abs/2202.04731 (2022).
3. Implemented preprocessing 3D microscopy videos of C.elegans into centroids graph by devolearn.
4. Fixed bugs of external modules.

## Details of what was done
### 1. Searched for previous researches and discussed with the mentors and contributors which graph expression and GNN structure are effective for cell tracking.
Our project has started as a research project and we spent a lot of time searching for previous researches and discussing which features of the target cells and which type of GNN structure are useful for effectively capture the development of organisms.
Here I summarize current idea about the characteristics of the cells, difficulties, and realistic approach.

Future plan:
* Apply to cell tracking Spatio-Temporal Graph Transformer used for tasks such as pedestrian tracking.
  * reference: Yu, C., Ma, X., Ren, J., Zhao, H. & Yi, S. Spatio-Temporal Graph Transformer Networks for Pedestrian Trajectory Prediction. Preprint at https://doi.org/10.48550/arXiv.2005.08514 (2020).
  *


:
* Each cell occupies some spaces and the locations of the centroids are decided by interactions between nearby cells.
* These interactions are assumed to be expressed by edges of the graphs, while the centroids of the cells are expressed by nodes.

### 2. Refactored inference part of the source codes of: Ben-Haim, T. & Riklin-Raviv, T. Graph Neural Network for Cell Tracking in Microscopy Videos. Preprint at http://arxiv.org/abs/2202.04731 (2022).


### 3. Implemented preprocessing 3D microscopy videos of C.elegans into centroids graph by devolearn.
- [Reported](https://github.com/LspongebobJH/DevoGraph/blob/wataru/stage_1/stage_1/stage_1.ipynb) ([commit](https://github.com/LspongebobJH/DevoGraph/commit/4b88c23f2fb9c4da7f633de5a94f946d4176d46e)) that devolearn does not generalize to other datasets. -> future work
  - [PR merged](https://github.com/LspongebobJH/DevoGraph/pull/1), [PR under review](https://github.com/LspongebobJH/DevoGraph/pull/5) (-> [screenshot])
- The commits are listed [here](https://github.com/DevoLearn/devolearn/pull/74).   (-> [screenshot](https://github.com/watarungurunnn/GSoC2022_submission/blob/main/Screen%20Shot%202022-09-12%20at%2011.45.27.png))

https://github.com/LspongebobJH/DevoGraph/commit/eac3368a6d9d4e982b2583cd6a1b23bbcc641f3d

### 4. Fixed bugs of external modules.
- devolearn - Installed package from the pip could not used as written in README.md, so added instruction to install from the source. [PR under review](https://github.com/DevoLearn/devolearn/pull/73)
- devolearn - Fixed wrong URL of the provided trained model. [PR merged](https://github.com/DevoLearn/devolearn/pull/67)
- scikit-image - Fixed a function of "regionprops" of scikit-image, which requires non-negative input, to consider negative value input very close to 0 to be 0. [Folk](https://github.com/scikit-image/scikit-image/commit/dede59c19817bceccf80de8eb59eb29db746e1c5)
  - The negative values appeared to be computational error.
  - This change was needed to run the cell-tracking-gnn on 3D datasets.
