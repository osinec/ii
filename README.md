---
license: llama3.1
datasets:
- marcelbinz/Psych-101
tags:
- Psychology
- unsloth
---





### Model Summary:

<p align="center">
  <img src="https://marcelbinz.github.io/imgs/centaur.png" width="200"/>
</p>

Llama-3.1-Centaur-70B is a foundation model of cognition model that can predict and simulate human behavior in any behavioral experiment expressed in natural language.

- **Paper:** [A foundation model to predict and capture human cognition](https://www.nature.com/articles/s41586-025-09215-4)
- **More Information:** [Documentation](https://marcelbinz.github.io/centaur)
- **Point of Contact:** [Marcel Binz](mailto:marcel.binz@helmholtz-munich.de)
         
### Usage:

Note that Centaur is trained on a data set in which human choices are encapsulated by "<<" and ">>" tokens. For optimal performance, it is recommended to adjust prompts accordingly.

The recommended usage is by loading the low-rank adapter using unsloth:

```python
from unsloth import FastLanguageModel

model_name = "marcelbinz/Llama-3.1-Centaur-70B-adapter"
model, tokenizer = FastLanguageModel.from_pretrained(
  model_name = model_name,
  max_seq_length = 32768,
  dtype = None,
  load_in_4bit = True,
)

FastLanguageModel.for_inference(model)
```

This requires 80 GB GPU memory. More details are provided in this [**example script**](https://github.com/marcelbinz/Llama-3.1-Centaur-70B/blob/main/test_adapter.py).

You can alternatively also directly use the less-tested [merged model](https://huggingface.co/marcelbinz/Llama-3.1-Centaur-70B).


### Licensing Information

[Llama 3.1 Community License Agreement](https://huggingface.co/meta-llama/Llama-3.1-70B-Instruct/blob/main/LICENSE)

### Citation Information

```
@misc{binz2024centaurfoundationmodelhuman,
      title={Centaur: a foundation model of human cognition}, 
      author={Marcel Binz and Elif Akata and Matthias Bethge and Franziska Brändle and Fred Callaway and Julian Coda-Forno and Peter Dayan and Can Demircan and Maria K. Eckstein and Noémi Éltető and Thomas L. Griffiths and Susanne Haridi and Akshay K. Jagadish and Li Ji-An and Alexander Kipnis and Sreejan Kumar and Tobias Ludwig and Marvin Mathony and Marcelo Mattar and Alireza Modirshanechi and Surabhi S. Nath and Joshua C. Peterson and Milena Rmus and Evan M. Russek and Tankred Saanum and Natalia Scharfenberg and Johannes A. Schubert and Luca M. Schulze Buschoff and Nishad Singhi and Xin Sui and Mirko Thalmann and Fabian Theis and Vuong Truong and Vishaal Udandarao and Konstantinos Voudouris and Robert Wilson and Kristin Witte and Shuchen Wu and Dirk Wulff and Huadong Xiong and Eric Schulz},
      year={2024},
      eprint={2410.20268},
      archivePrefix={arXiv},
      primaryClass={cs.LG},
      url={https://arxiv.org/abs/2410.20268}, 
}
```

[<img src="https://raw.githubusercontent.com/unslothai/unsloth/main/images/unsloth%20made%20with%20love.png" width="200"/>](https://github.com/unslothai/unsloth)