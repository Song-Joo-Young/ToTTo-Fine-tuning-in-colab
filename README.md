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
| t5-base [LoRA fine-tuning]  | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]() | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]() |
| LATTICE(t5-small)           | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]()                             |
| LATTICE(t5-base)            | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]()                             |


<h3>Models</h3>
<table>
  <thead>
    <tr>
      <th>Model</th>
      <th>Train Colab Link</th>
      <th>Evaluation Link</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>t5-small [Full fine-tuning]</td>
      <td><a href="https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-small_Full-fine-tuning/train/ToTTo_T5_small_Fine_tuning_10epoch.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></td>
      <td><a href="https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-small_Full-fine-tuning/evaluation/ToTTo_T5_small_Evaluation.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></td>
    </tr>
    <tr>
      <td>t5-small [LoRA fine-tuning]</td>
      <td><a href="https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-small_LoRA-fine-tuning/train/ToTTo_T5_small_LoRA_Fine_tuning_10epoch.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></td>
      <td><a href="https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-small_LoRA-fine-tuning/evaluation/ToTTo_T5_small(LoRA)_10epoch_Evaluation.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></td>
    </tr>
    <tr>
      <td>t5-base [Full fine-tuning]</td>
      <td><a href="https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-base_Full-fine-tuning/train/ToTTo_T5_base_Fine_tuning_5epoch.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></td>
      <td><a href="https://colab.research.google.com/github/Song-Joo-Young/ToTTo-Fine-tuning-in-colab/blob/main/t5-base_Full-fine-tuning/evaluation/ToTTo_t5-base_Evaluation.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></td>
    </tr>
    <tr>
      <td>t5-base [LoRA fine-tuning]</td>
      <td><a href="#"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></td>
      <td><a href="#"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></td>
    </tr>
    <tr>
      <td rowspan="2">LATTICE(t5-small)</td>
      <td colspan="2"><a href="#"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></td>
    </tr>
    <tr>
      <td colspan="2"></td>
    </tr>
    <tr>
      <td rowspan="2">LATTICE(t5-base)</td>
      <td colspan="2"><a href="#"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></td>
    </tr>
    <tr>
      <td colspan="2"></td>
    </tr>
  </tbody>
</table>



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

#### Reference
* T5: Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer ([T5 Paper](https://arxiv.org/abs/1910.10683))
* LATTICE: Robust (Controlled) Table-to-Text Generation with Structure-Aware Equivariance Learning ([LATTICE Paper](https://arxiv.org/abs/2205.03972))
* ToTTo: A Controlled Table-To-Text Generation Dataset ([ToTTo Paper](https://arxiv.org/abs/2004.14373) / [ToTTo GitHub Repository](https://github.com/google-research-datasets/ToTTo))
* ToTTo Evaluation supplementary repository ([GitHub Repository](https://github.com/google-research/language/tree/master/language/totto))
* BLEURT: a Transfer Learning-Based Metric for Natural Language Generation ([GitHub Repository](https://github.com/google-research/bleurt?tab=readme-ov-file#bleurt-a-transfer-learning-based-metric-for-natural-language-generation))
* BLUERT Cheackpoints ([GitHub Repository](https://github.com/google-research/bleurt/blob/master/checkpoints.md))
