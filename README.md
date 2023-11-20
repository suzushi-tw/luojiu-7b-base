---
license: apache-2.0
base_model: Meta/Llama2
tags:
- Short shift attention
- Qlora
- Pretrain Stage
model-index:
- Dataset size: 6Gb 
  Train/loss: 1.3
---

# 落九(Base): 繁體中文預訓練模型

## 簡介
**落九** 是一個繁體中文模型，Backbone為Llama2，雖然目前有許多開源的語言模型Base，但是部分Paper表明Llama2的學習速度比大部分語言模型快，
且Hallucination(幻想)的指標僅落後於GPT和Llama2-70b。期待這個語言模型能越來越好!


**落九**名稱來源於李白的《望廬山瀑布》：**飛流直下三千尺，疑是銀河落九天**。
```text
《望廬山瀑布》 
 唐.李白
日照香爐生紫煙，遙看瀑布掛前川。
飛流直下三千尺，疑是銀河落九天。
```

<!-- This model card has been generated automatically according to the information the Trainer had access to. You
should probably proofread and complete it, then remove this comment. -->

# 使用方法

去Meta 官網獲得Llama2 授權，Merge Lora weight後獲得可以用的模型

# 訓練細節/Training Detail

基於紅樓夢擴充的61388大詞表，後經過QLora和Short shift Attention訓練，僅使用一張Ａ１０顯卡。
經過 int 4 量化和 Lora Weight 32訓練時大約使用１８ＧＢ記憶體。

## Model description

預訓練於6GB CC　Dataset,尚未經過ＳＦＴ訓練

## Intended uses & limitations

This is intended to contribute towards the Traditional Chinese Language model, most language model now days are mostly trained on 
Simplified Chinese, as a result, most of the time they only answer in Simplified Chinese, a model that fits for Taiwanese use case 
is lacking. Yet the challenge is far greater then what most people might expect to train a traditional Chinese model, the lack of dataset
, and resoucres are generally a concern. Hence the creation of this project and model. Since the model hasn't gone thorugh sft stage yet,
please stay tuned while I am working on the sft training. 

## Training and evaluation data

This is trained on filtered cc dataset, the model hasn't gone through evalutaion yet, all the testing will be done
once the sft stage is completed.

## Training procedure

### Training hyperparameters

The following hyperparameters were used during training:
- learning_rate: 5e-05
- train_batch_size: 8
- eval_batch_size: 8
- gradient_accumulation_steps: 4
- total_train_batch_size: 32
- optimizer: Adam with betas=(0.9,0.999) and epsilon=1e-08
- lr_scheduler_type: cosine
- num_epochs: 3.0
- lora: 32
- total steps: 8712

### Training results

Trained with 3 epochs 

<img src="./pictures\trainloss.png" width="700">


### Framework versions

- Transformers 4.34.1
- Pytorch 1.13.1
- Datasets 2.14.7
- Tokenizers 0.14.1
