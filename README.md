---
license: apache-2.0
base_model: suzushi/luojiu-7b_Tokenize_stage
tags:
- llama-factory
- lora
- generated_from_trainer
model-index:
- name: results66
  results: []
---

<!-- This model card has been generated automatically according to the information the Trainer had access to. You
should probably proofread and complete it, then remove this comment. -->

# results66

This model is a fine-tuned version of [suzushi/luojiu-7b_Tokenize_stage](https://huggingface.co/suzushi/luojiu-7b_Tokenize_stage) on the c4tw-taiwan-llama dataset.

## Model description

More information needed

## Intended uses & limitations

More information needed

## Training and evaluation data

More information needed

## Training procedure

### Training hyperparameters

The following hyperparameters were used during training:
- learning_rate: 5e-05
- train_batch_size: 8
- eval_batch_size: 8
- seed: 42
- gradient_accumulation_steps: 4
- total_train_batch_size: 32
- optimizer: Adam with betas=(0.9,0.999) and epsilon=1e-08
- lr_scheduler_type: cosine
- num_epochs: 3.0

### Training results



### Framework versions

- Transformers 4.34.1
- Pytorch 1.13.1
- Datasets 2.14.7
- Tokenizers 0.14.1
