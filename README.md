# LoRA-Select: Adaptive Task-Specific Text Generation with Dynamic LoRA Switching

This repository contains the implementation of LoRA-Select, a dynamic Mixture-of-Experts (MoE) framework using Low-Rank Adaptation (LoRA) for domain-specific language model adaptation.

## Overview

LoRA-Select addresses efficiency, adaptability, and domain specialization challenges in Large Language Models by:
- Training lightweight, domain-specific adapters instead of expensive full fine-tuning
- Dynamically activating relevant adapters during inference using a domain classifier
- Optimizing task performance with reduced memory usage
- Enabling modular integration of new domains without base model retraining

## Project Components

- **Base Model**: Mistral-7B with 4-bit quantization
- **Domain Adapters**: Fine-tuned LoRA adapters (r=16, alpha=32) for:
  - Legal domain (740 steps)
  - Finance domain (500 steps)
  - Healthcare domain (400 steps)
- **Domain Classifier**: Zero-shot ComprehendIt model for query classification
- **Memory Optimization**: Dynamic loading of only the selected domain adapter
- **User Interface**: Gradio-based interface for user interaction

## Repository Structure

- `adapter_tuning/`: Python notebooks for domain specific adapter training and evaluation
- `LoRA_Select_Dynamic_Switch.ipynb`: Putting it all together - Uses Gradio UI 
- `DS5983_Presentation_LoRA-SELECT.pdf`: The presentation pdf used for the pitch in our demo video

## Trained Models

The fine-tuned LoRA adapters are available on Hugging Face:
- [lora-mistral-legal](https://huggingface.co/vaibhav1/lora-mistral-legal)
- [lora-mistral-finance](https://huggingface.co/vaibhav1/lora-mistral-finance)
- [lora-mistral-medical](https://huggingface.co/vaibhav1/lora-mistral-medical)

## Datasets

This project uses the following datasets:
1. [Legal QA](https://huggingface.co/datasets/dzunggg/legal-qa-v1)
2. [Finance Alpaca](https://huggingface.co/datasets/gbharti/finance-alpaca)
3. [ChatDoctor-200k](https://huggingface.co/datasets/LinhDuong/chatdoctor-200k)

## Demo

A video demonstration is available [here](https://drive.google.com/file/d/1E_-pP9bzyD8HX29Fu2PZe15hEACO47WP/view).

## Important Note

**Due to the interactive widgets used in our notebooks, GitHub may not render them properly within the browser. Please download the notebooks and run them locally for the best experience.**

## Contributors

- Vaibhav Thalanki 
- Lakshmi Vadhanie G 
- Akshara Reddy 

## References

1. Dzunggg. legal-qa-v1. Hugging Face, 2024, huggingface.co/datasets/dzunggg/legal-qa-v1
2. Bharti, Gaurang. finance-alpaca (Revision 51d16b6). 2024. Hugging Face, https://huggingface.co/datasets/gbharti/finance-alpaca
3. Li, Yunxiang, et al. "ChatDoctor: A medical chat model fine-tuned on a large language model meta-ai (llama) using medical domain knowledge." Cureus 15.6 (2023)

## License

This project is available under the MIT License.
