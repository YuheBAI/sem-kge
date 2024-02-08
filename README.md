
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](./LICENSE)

Documentation on DGL-KE can be found at [Documentation](https://dglke.dgl.ai/doc/).

## Overview

This is the repository for our paper ["A Semantic Partitioning Method for Large-Scale Training of Knowledge Graph Embeddings"](https://dl.acm.org/doi/abs/10.1145/3543873.3587537). The code extends the knowledge graph embedding library DGL-KE and implemented a semantic partitioning method for parallel training on the repository. 


## Quick Start


To install the latest version of SEM-KGE run:

```
conda create -n sem-kge python=3.8
conda activate sem-kge
pip3 install torch
pip3 install dgl==0.6.1
cd python/
python3 setup.py install
cd ..
```

Train a `DistMult` model on `FB15k` dataset using `Semantic Partitioning` by running the following command:

```
dglke_train --model_name DistMult --dataset FB15k --batch_size 1000 \
--neg_sample_size 200 --hidden_dim 400 --gamma 143.0 --lr 0.08 --max_step 5000 --log_interval 100 \
--batch_size_eval 16 --test -adv --num_thread 1 --num_proc 8 --sem_part 
```

This command will train the `DistMult` model on the `FB15k` dataset and save the trained embeddings into the file.


## Cite

If you use Sem-kge in a scientific publication, we would appreciate citations to the following paper:

```bibtex
@inproceedings{Sem-kge,
author = {Bai, Yuhe},
title = {A Semantic Partitioning Method for Large-Scale Training of Knowledge Graph Embeddings},
year = {2023},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
booktitle = {Companion Proceedings of the ACM Web Conference 2023},
pages = {573–577},
series = {WWW '23 Companion}
}
```

## License

This project is licensed under the Apache-2.0 License.
