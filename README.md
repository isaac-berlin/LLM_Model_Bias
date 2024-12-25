# Exploring Political Bias in LLMs Through Debate: A Multi-Agent Framework

This project investigates the performance of fine-tuned large language models (LLMs) with distinct left-leaning and right-leaning political biases in structured debates on politically sensitive topics. Leveraging models such as LLAMA 3.2 and PHI 1.5, we analyze their adherence to predefined biases, reasoning capabilities, and persuasiveness within a multi-agent framework and through automated evaluation metrics.

A comprehensive overview of the methodologies, results, and models used in this project, as well as the final paper, is available [here](https://isaac-berlin.github.io/LLM_Model_Bias/). This work was conducted as part of the final project for the course CSCI 5541: Natural Language Processing. We extend our gratitude to Professor Dongyeop Kang and the teaching assistants for their invaluable guidance and support throughout the project.

## Structure

### Finetuning Data

In this project, we required left-leaning, right-leaning, and neutral LLM agents. To achieve this, we generated separate datasets to fine-tune each type of model. We utilized the [BABE](https://paperswithcode.com/dataset/babe) dataset, which consists of sentences from left- and right-leaning news organizations with varying levels of bias. The sentences were partitioned into left-leaning and right-leaning subsets, with each respective model fine-tuned on their own subset. The resulting dataset partitions are available in the `src/data` directory.

### LLMs

For this project, we fine-tuned left, right, and center versions of two open-source LLMs: [LLama 3.2](https://huggingface.co/meta-llama/Llama-3.2-1B) and [Phi 1.5](https://huggingface.co/microsoft/phi-1_5). These models, developed by Meta and Microsoft respectively, were selected for their similarity to other state-of-the-art models, providing a representative basis for our experiments.

### Debate Arena

We designed a custom debate arena object tailored for this task. The framework is compatible with any Hugging Face LLM model for text generation. The code for the debate arena, along with an example usage, is available in the `src/debate_arena.ipynb` file. While the framework was employed for political-style debates in this project, it is adaptable to any topic. The class instantiation allows users to configure response length, the number of debate turns, and the temperature of model responses.
