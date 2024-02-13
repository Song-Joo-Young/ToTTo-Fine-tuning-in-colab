# ToTTo Fine-tuning in colab
ToTTo is an open-domain English table-to-text dataset with over 120,000 training examples that proposes a controlled generation task: given a Wikipedia table and a set of highlighted table cells, produce a one-sentence description from Google Research. 

This repository serves as the hub for the ToTTo dataset, offering a collection of diverse T5-base models fine-tuned on the ToTTo dataset. We present a comparative analysis of various T5-base models and state-of-the-art (SOTA) models to assess their performance on the controlled table-to-text generation task proposed by ToTTo.

In addition, for beginners to learn easily, all tasks come with Colab notebooks for seamless execution.

### Dataset
```bash
!wget https://storage.googleapis.com/totto-public/totto_data.zip
!unzip totto_data.zip
```

### Models
| Model                       | Train Colab Link | Evaluation Link |
|-----------------------------|------------------|-----------------------|
| t5-small [Full fine-tuning] | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-small_Full-fine-tuning/train/ToTTo_T5_small_Fine_tuning_10epoch.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-small_Full-fine-tuning/evaluation/ToTTo_T5_small_Evaluation.ipynb) |
| t5-small [LoRA fine-tuning] | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-small_LoRA-fine-tuning/train/ToTTo_T5_small_LoRA_Fine_tuning_10epoch.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-small_LoRA-fine-tuning/evaluation/ToTTo_T5_small(LoRA)_10epoch_Evaluation.ipynb) |
| t5-base [Full fine-tuning]  | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-base_Full-fine-tuning/train/ToTTo_T5_base_Fine_tuning_5epoch.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-base_Full-fine-tuning/evaluation/ToTTo_t5-base_Evaluation.ipynb) |
| t5-base [LoRA fine-tuning]  | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-base_LoRA-fine-tuning/train/ToTTo_T5_base_LoRA_Fine_tuning_3epoch.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-base_LoRA-fine-tuning/evaluation/ToTTo_T5_base(LoRA)_3epoch_Evaluation.ipynb) |
| LATTICE(t5-small)           | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/LATTICE/t5-small/ToTTo_LATTICE_t5_small.ipynb) | - |
| LATTICE(t5-base)            | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/LATTICE/t5-base/ToTTo_LATTICE_t5_base.ipynb) | - |




### Metrics
* BLEU
* PARENT
* BLEURT
  * Requirements  
    ```bash
    !git clone https://github.com/Song-Joo-Young/language.git language_repo
    !pip install git+https://github.com/google-research/bleurt.git
    %cd language_repo
    # Downloads the BLEURT-base checkpoint.
    !wget https://storage.googleapis.com/bleurt-oss-21/BLEURT-20.zip .
    !unzip BLEURT-20.zip
    !pip3 install -r language/totto/eval_requirements.txt
    ```

   * To evaluate
     ```bash
     !bash language/totto/totto_eval.sh --prediction_path /content/drive/MyDrive/ToTTo_T5-base/generation_dev_epoch.txt --target_path /content/drive/MyDrive/ToTTo_T5-base/totto_dev_data.jsonl
     ```

### Results
| Model               | BLEU | PARENT | BLEURT | BLEU (Overlap) | PARENT (Overlap) | BLEURT (Overlap) | BLEU (Non-Overlap) | PARENT (Non-Overlap) | BLEURT (Non-Overlap) |
|---------------------|------|--------|--------|----------------|------------------|------------------|--------------------|----------------------|----------------------|
| T5-small            | 44.9 | 55.96  | 0.6514 | 52.0           | 59.91            | 0.6908           | 38.0               | 52.15                | 0.6134               |
| T5-small (LoRA)     | 42.2 | 53.96  | 0.6340 | 48.9           | 57.50            | 0.6721           | 35.7               | 50.55                | 0.5973               |
| LATTICE (T5-small)  | 47.4 | 57.8   | -      | 55.6           | 62.3             | -                | 39.1               | 53.3                 | -                    |
| T5-base             | 47.3 | 57.73  | 0.6677 | 54.9           | 61.52            | 0.7050           | 40.0               | 54.06                | 0.6318               |
| T5-base (LoRA)      | 44.7 | 56.08  | 0.6530 | 51.6           | 59.82            | 0.6893           | 38.0               | 52.47                | 0.6180               |
| LATTICE (T5-base)   | 48.4 | 58.1   | -      | 56.1           | 62.4             | -                | 40.4               | 53.9                 | -                    |

* LATTICE result : [ToTTo Official Leaderboard](https://github.com/google-research-datasets/ToTTo?tab=readme-ov-file) refer to Results

| Model              | t5-small Full fine-tuning | t5-small LoRA | t5-small LATTICE | t5-base Full fine-tuning | t5-base LoRA | t5-base LATTICE |
|--------------------|---------------------------|---------------|------------------|--------------------------|--------------|-----------------|
| **Epoch**          | 10                        | 10            | -                | 5                        | 3            | -               |
| **Learning rate**  | 0.0001                    | 0.001         | -                | 0.0001                   | 0.001        | -               |
| **Batch size**     | 16                        | auto find     | -                | 8                        | auto find    | -               |
| **Learning Time**  | 12:44:05                  | 9:40:07       | -                |                          | 10:09:47     | -               |

* Training parameter: LoRA Tuning Seq2SeqTrainingArguments - `auto_find_batch_size = True`. LATTICE provides code only due to a lack of GPU tokens. [ToTTo Official Leaderboard](https://github.com/google-research-datasets/ToTTo?tab=readme-ov-file) refer to Results



### Appendix
* Full Fine-tuning Visualization



#### Reference
* T5: Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer ([T5 Paper](https://arxiv.org/abs/1910.10683))
* LATTICE: Robust (Controlled) Table-to-Text Generation with Structure-Aware Equivariance Learning ([LATTICE Paper](https://arxiv.org/abs/2205.03972))
* ToTTo: A Controlled Table-To-Text Generation Dataset ([ToTTo Paper](https://arxiv.org/abs/2004.14373) / [ToTTo GitHub Repository](https://github.com/google-research-datasets/ToTTo))
* ToTTo Evaluation supplementary repository ([GitHub Repository](https://github.com/google-research/language/tree/master/language/totto))
* BLEURT: a Transfer Learning-Based Metric for Natural Language Generation ([GitHub Repository](https://github.com/google-research/bleurt?tab=readme-ov-file#bleurt-a-transfer-learning-based-metric-for-natural-language-generation))
* BLUERT Cheackpoints ([GitHub Repository](https://github.com/google-research/bleurt/blob/master/checkpoints.md))
