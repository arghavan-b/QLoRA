# Fine-Tuning Llama 3.1-8B with LoRA and Unsloth
This repository provides code and instructions for fine-tuning the Llama 3.1-8B language model using Low-Rank Adaptation (LoRA) and Unsloth.
We employ LoRA with a rank of 16 and apply 4-bit quantization to optimize for efficiency without significantly sacrificing performance.

## Unsloth

[Unsloth](https://github.com/unslothai/unsloth) is a lightweight and efficient library designed to optimize and accelerate the training and inference of large language models (LLMs). It provides tools for:

- **Quantization**: Reducing model size and computational requirements through techniques like 4-bit quantization.
- **Memory Optimization**: Efficient memory management to enable training of large models on consumer-grade hardware.
- **Fine-Tuning Support**: Simplifies the fine-tuning process with support for methods like LoRA.

By integrating Unsloth, we can fine-tune large models like Llama 3.1-8B more efficiently.

## Dataset: [dialogsum](https://huggingface.co/datasets/knkarthick/dialogsum)
DialogSum is a large-scale dialogue summarization dataset, consisting of 13,460 (Plus 100 holdout data for topic generation) dialogues with corresponding manually labeled summaries and topics.
###Data Fields

- dialogue: text of dialogue.
- summary: human written summary of the dialogue.
- topic: human written topic/one liner of the dialogue.
- id: unique file id of an example.
## Fine-Tuning Setup

### LoRA (Low-Rank Adaptation)

We use LoRA with a rank of 16 to fine-tune the model. LoRA reduces the number of trainable parameters by decomposing weight updates into low-rank matrices, significantly lowering the computational and memory overhead.

### 4-bit Quantization

Applying 4-bit quantization reduces the model's memory footprint and speeds up computation. This allows for efficient training and inference on hardware with limited resources.

## Getting Started

### Prerequisites

- **Python 3.7** or higher
- **PyTorch**
- **CUDA** (for GPU acceleration)
- **Unsloth**


### Installation

  **Install Required Packages**

   ```bash
   !pip install unsloth
   # Also get the latest nightly Unsloth!
   !pip install --upgrade --no-cache-dir "unsloth[colab-new] @ git+https://github.com/unslothai/unsloth.git"
   ```

  
## Fine-Tuning the Model


## Results


## Dependencies

List of major dependencies:

- `torch`
- `unsloth`
- `transformers`
- `datasets`
- `peft` (for LoRA)
- `trl`

## Acknowledgments

- **Unsloth**: [GitHub Repository](https://github.com/unslothai/unsloth)
- **Unsloth Code**:[Google Colab](https://colab.research.google.com/drive/1Ys44kVvmeZtnICzWz0xgpRnrIOjZAuxp?usp=sharing#scrollTo=95_Nn-89DhsL)
- **DialogSum Dataset**: [Hugging face]([https://github.com/yahma/alpaca-cleaned](https://huggingface.co/datasets/knkarthick/dialogsum))
- **LoRA: Low-Rank Adaptation of Large Language Models**: [Paper](https://arxiv.org/abs/2106.09685)
- **Llama Language Model**:[Paper](https://scontent-sjc3-1.xx.fbcdn.net/v/t39.2365-6/453304228_1160109801904614_7143520450792086005_n.pdf?_nc_cat=108&ccb=1-7&_nc_sid=3c67a6&_nc_ohc=1_dorvk2IWsQ7kNvgHIoTw5&_nc_ht=scontent-sjc3-1.xx&_nc_gid=A4ed2PbeZBauri6k5FpNxFl&oh=00_AYA0r-47FNnOqgHRhBWFMu3ifWxPKNlCxQD_OPk940e7Dw&oe=670F5107)

## License

[MIT License](LICENSE)
