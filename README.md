# FewRel-Adv-ML
Meta Learning on FewRel Dataset in Euclidean and Non Euclidean Space

## Data

The dataset has already be contained in the github repo. However, due to the large size, glove files (pre-trained word embeddings) and BERT pretrain checkpoint are not included. Please download `pretrain.tar` from [here](https://drive.google.com/file/d/1QbocSumLcA-krPUSYEGxw_TMI0N9l5SQ/view?usp=sharing) and put it under the root. Then run `tar xvf pretrain.tar` to decompress it.

## Training and Evaluating the model in Euclidean space
```bash
python train_euclidean.py \
    --trainN 5 --N 5 --K 1 --Q 1 \
    --model pair --encoder bert --pair --hidden_size 768 --val_step 1000 \
    --batch_size 4 \
```

## Training and Evaluating the model in Non Euclidean space

Stiefel + rSGD
```bash
python train_noneuclidean.py \
    --trainN 5 --N 5 --K 1 --Q 1 \
    --model pair_ne --encoder bert --pair --hidden_size 768 --val_step 1000 \
    --batch_size 4 \
```

Stiefel + rAdagrad
```bash
python train_noneuclidean.py \
    --trainN 5 --N 5 --K 1 --Q 1 \
    --model pair_ne --encoder bert --pair --hidden_size 768 --val_step 1000 \
    --batch_size 4 --optim adagrad \
```

Hyperbolic + rSGD
```bash
python train_noneuclidean_hyperbolic.py \
    --trainN 5 --N 5 --K 1 --Q 1 \
    --model pair_ne --encoder bert --pair --hidden_size 768 --val_step 1000 \
    --batch_size 4 \
```

Hyperbolic + rAdagrad
```bash
python train_noneuclidean_hyperbolic.py \
    --trainN 5 --N 5 --K 1 --Q 1 \
    --model pair_ne --encoder bert --pair --hidden_size 768 --val_step 1000 \
    --batch_size 4 --optim adagrad \
```
    
