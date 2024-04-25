**Finetuning LLaMA-3 8B with LoRA and UnSloth**
=====================================================

This repository serves as a comprehensive guide on how to fine-tune the LLaMA-3 model on specific downstream tasks. It includes the necessary code for fine-tuning the LLaMA-3 8B model using LoRA technique.

**Model Description**
--------------------

The LLaMA-3 8B model is a powerful language model created by Meta AI. It was fine-tuned just two days after its initial release. Trained on a dataset containing 120,000 coding examples, this model ensures high-quality results for coding tasks.

**Fine-tuning with UnSloth**

To fine-tune the LLaMA-3 8B model, we utilized the UnSloth tool, which significantly reduced the memory requirements for fine-tuning. By leveraging UnSloth's 4-bit format, we were able to fine-tune the model using a fraction of the memory needed for traditional fine-tuning methods.

*Comparison to 16-bit Model*

In contrast, our stored model uses the traditional 16-bit format, which results in a larger model size. This highlights the memory efficiency of the UnSloth technique, making it an attractive option for fine-tuning large language models like LLaMA-3 8B.


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

The model is available [here](https://huggingface.co/kiko2001/llama-3-coding-mkd), on the Hugging Face Model Hub.
