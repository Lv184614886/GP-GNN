# Graph Neural Networks with Generated Parameters for Relation Extraction

Code and dataset of ACL2019 Paper **Graph Neural Networks with Generated Parameters for Relation Extraction.** [paper](https://www.aclweb.org/anthology/P19-1128.pdf)



## Citation

Please cite our paper if you find it helpful.

```
@inproceedings{zhu2019graph,
  title={Graph Neural Networks with Generated Parameters for Relation Extraction},
  author={Zhu, Hao and Lin, Yankai and Liu, Zhiyuan and Fu, Jie and Chua, Tat-Seng and Sun, Maosong},
  booktitle={Proceedings of ACL},
  year={2019}
}
```

This repository is mainly contributed by [Hao Zhu](http://www.zhuhao.me/), Daniil Sorokin.



## Dataset

Please download `gpgnn_data.zip` from [Aliyun](https://thunlp.oss-cn-qingdao.aliyuncs.com/gpgnn_data.zip) and unzip it as the `data` folder:

```
unzip gpgnn_data.zip
```



## Requirements and Installation

This repository has been tested with `Python 3.6`,`torch==1.4.0`,`sacred==0.8.1`

```
pip3 install -r requirements.txt
```



## Get Started

### Directory structure

>**models/**: Baseline models (LSTM, CNN, PCNN, ContextAware) in `baselines.py` and  GPGNN model in `our_models.py`.
>
>**parsing/**: APIs to convert graphs into Tensors which can be fed into our models.
>
>**result/**: used to store models and output results on the testset. 
>
>**semanticgraph/**: APIs to construct relation graphs from sentences.
>
>**utils/**: APIs to load word embeddings, evaluate and operate the graphs.
>
>**model_param.json**: Hyper parameters for the models.



### Running

**train**:

The parameters of the function `main` are set in function `main_config`. You can modify the parameters in `main_config` to train different models. And the hyper parameters for the models are stored in `model_params.json`.

```bash
python3 train.py
```

**test**:

Before testing, you should choose proper version of the model by modifing the `load_model` in `main_config`.

```bash
python3 test.py
```

**evaluate**:

```bash
cd result
python3 test_accuracy.py --input (result_file_path)
```





