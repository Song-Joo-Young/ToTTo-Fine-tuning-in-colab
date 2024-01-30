# ToTTo Fine-tuning in colab
ToTTo is an open-domain English table-to-text dataset with over 120,000 training examples that proposes a controlled generation task: given a Wikipedia table and a set of highlighted table cells, produce a one-sentence description from Google Research. 

This repository serves as the hub for the ToTTo dataset, offering a collection of diverse T5-base models fine-tuned on the ToTTo dataset. We present a comparative analysis of various T5-base models and state-of-the-art (SOTA) models to assess their performance on the controlled table-to-text generation task proposed by ToTTo.

In addition, for beginners to learn easily, all tasks come with Colab notebooks for seamless execution.

#### Reference
* ToTTo: A Controlled Table-To-Text Generation Dataset ([ToTTo Paper](https://arxiv.org/abs/2004.14373) / [ToTTo GitHub Repository](https://github.com/google-research-datasets/ToTTo))
* ToTTo Evaluation supplementary repository : [GitHub Repository](https://github.com/google-research/language/tree/master/language/totto)



### Models
* t5-base [Full fine-tuning]
* t5-large [LoRA fine-tuning]
* LATTICE(t5-base)


### Metrics
* BLEU
* PARENT
* BLEURT


### Results
