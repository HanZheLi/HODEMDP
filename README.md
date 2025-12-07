# HODE-MDP
The repository for Hypergraph ODE-based Multi-aspect User Dynamic Preference Modeling for Next POI Recommendation.

## Requirements

+ Pytorch 1.13.0
+ torchdiffeq 0.2.3
+ scikit-learn 0.23.2
+ scipy 1.10.1
+ pandas 1.5.3
+ numpy 1.24.3

### Create a virtual environment with conda
`conda create -n hode-mdp python=3.8`

`conda activate hode_mdp`

### Install PyTorch (adjust CUDA version as needed)
`conda install pytorch==1.13.0 torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia`

### Install other dependencies
`pip install torchdiffeq==0.2.3 scikit-learn==0.23.2 scipy==1.10.1 pandas==1.5.3 numpy==1.24.3`

## Datasets
We evaluate on four real-world LBSN datasets:

| Dataset | #Users | #POIs | #Check-ins | Sparsity |
|---------|--------|-------|------------|----------|
| NYC     | 834    | 3,835 | 44,686     | 98.61%   |
| TKY     | 2,173  | 7,038 | 308,566    | 97.82%   |
| SH      | 10,251 | 11,535| 303,635    | 99.74%   |
| Gowalla | 38,857 | 102,077| 1,911,888 | 99.95%   |

### Data Preprocessing
We provide the preprocessed NYC dataset, which is located in datasets/NYC/. 

`train_session_label.pkl`: Training sessions with labels

`valid_session_label.pkl`: Validation sessions

`test_poi_zero.txt`: Test sessions

`NYC_pois_coos_poi_zero.pkl`: POI coordinates

Each user’s trajectory is divided into sessions, where consecutive check-ins within a 24-hour interval belong to the same session.

## Running 
run HODE-MDP on NYC: `python run.py --dataset NYC --t1 7 --t2 14 --t3 7 --lambda_cl 0.4`

run HODE-MDP on TKY: `python run.py --dataset TKY --t1 7 --t2 5 --t3 7 --lambda_cl 0.3`


