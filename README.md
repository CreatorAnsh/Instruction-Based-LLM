# Instruction-Tuned GPT-2 Medium (Experimental)

This repository contains an instruction-tuned language model based on the **GPT-2 Medium** architecture. The model was fine-tuned for **2 epochs** on a custom instruction dataset to explore the effectiveness of small-scale instruction tuning. It is intended for **research and diagnostic purposes** only.

## Model Overview

- **Base model**: GPT-2 Medium (355M parameters)  
- **Training**: Instruction fine-tuning  
- **Epochs**: 2  
- **Evaluation method**: Automated evaluation by a larger language model  
- **Performance rating**: 1.25 (on a scale from 1 to 5)  
- **Intended use**: Experimental, for analysis and benchmarking of instruction-tuning methods at small scale  

## Limitations

This model is in an early experimental stage and has received a low performance rating (**1.25**) in automated evaluation. Key limitations include:

- Limited ability to follow or generalize instructions  
- Incoherent or inconsistent responses in complex tasks  
- Undertrained due to short training duration and possible dataset limitations  

**Note**: The model is **not suitable for production use**.

## Repository Structure
```
model/ # Pretrained model weights (if available)
config/ # Training configuration files
data/ # Dataset samples or preprocessing scripts
scripts/ # Training and evaluation utilities
README.md # Project documentation and usage instructions
```

## Usage Example

```python
from transformers import GPT2Tokenizer, GPT2LMHeadModel

tokenizer = GPT2Tokenizer.from_pretrained('path_to_model')
model = GPT2LMHeadModel.from_pretrained('path_to_model')

input_text = "Instruction: Explain the water cycle."
inputs = tokenizer(input_text, return_tensors="pt")
outputs = model.generate(**inputs)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```
### Future Work
Extend training epochs and improve dataset diversity

Conduct human evaluations alongside LLM-based assessments

Compare performance across various instruction tuning strategies

Fine-tune with reward models or alignment techniques
