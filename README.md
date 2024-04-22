**Finetuning LLaMA-3 8B with LoRA and UnSloth**
=====================================================

This repository can be used as an example on how to fine-tune LLaMA-3 on downstream task. It contains the code and model weights for finetuning the LLaMA-3 8B model with LoRA and UnSloth techniques. The whole proccess was done on Tesla T4 GPU with 15GB RAM.

## *DISCLAIMER*


The contents provided are solely for educational purposes. The model and dataset utilized in this project were extensive, and due to resource limitations, the conditions for comprehensive testing may not have been met. 

**Model Description**
--------------------

The LLaMA-3 8B model is a powerful language model created by Meta AI. It was fine-tuned just two days after its initial release. Trained on a dataset containing 120,000 coding examples, this model ensures high-quality results for coding tasks.



**Finetuning Details**
---------------------

* **Model:** LLaMA-3 8B
* **Dataset:** iamtarun/code_instructions_120k_alpaca
* **Training Args:**
    + `per_device_train_batch_size`: 2
    + `gradient_accumulation_steps`: 4
    + `warmup_steps`: 5
    + `max_steps`: 60
    + `learning_rate`: 2e-4
    + `fp16`: [True/False]
    + `bf16`: [True/False]
    + `logging_steps`: 1
    + `optim`: "adamw_8bit"
    + `weight_decay`: 0.01
    + `lr_scheduler_type`: "linear"
    + `seed`: 3407
    + `output_dir`: "outputs"


**Model Hub**
-------------

This model is available on the Hugging Face Model Hub: kiko2001/llama-3-coding-mk
