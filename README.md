# Transformers-tutorials

Hi there folks!

This repository contains demo(s) to the models I ported to the [Transformers library](https://github.com/huggingface/transformers) by 🤗 HuggingFace. Currently, all of them are implemented in PyTorch.

NOTE: This readme has been highly inspired from @[NielsRogge](https://github.com/NielsRogge) [transformers-tutorials repo](https://github.com/NielsRogge/Transformers-Tutorials/tree/master).

NOTE: if you are not familiar with HuggingFace and/or Transformers, I highly recommend to check out the [free course](https://huggingface.co/course/chapter1) they provide, which introduces you to several Transformer architectures (such as BERT, GPT-2, T5, BART, etc.), as well as an overview of the HuggingFace libraries, including [Transformers](https://github.com/huggingface/transformers), [Tokenizers](https://github.com/huggingface/tokenizers), [Datasets](https://github.com/huggingface/datasets), [Accelerate](https://github.com/huggingface/accelerate) and the [hub](https://huggingface.co/).

For an overview of the ecosystem of HuggingFace for computer vision (June 2022), refer to [this notebook](https://github.com/NielsRogge/Transformers-Tutorials/blob/master/HuggingFace_vision_ecosystem_overview_(June_2022).ipynb) with corresponding [video](https://www.youtube.com/watch?v=oL-xmufhZM8&t=2884s).

Currently, it contains the following demos:
* Transformers are Sample-Efficient World Models (IRIS) ([paper]([https://arxiv.org/abs/2104.01778](https://arxiv.org/abs/2209.00588))): 
  - train `IrisModel` on Atari environment(s) to play breakout or any environment id provided. [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/RUFFY-369/Transformers-tutorials/blob/main/IRIS/train_Iris_agent_on_atari.ipynb)

## Training frameworks
Regarding fine-tuning Transformer models (or more generally, PyTorch models), there are a few options:
- [HuggingFace Trainer](https://huggingface.co/transformers/main_classes/trainer.html). The HuggingFace Trainer API can be seen as a framework similar to PyTorch Lightning in the sense that it also abstracts the training away using a Trainer object. However, contrary to PyTorch Lightning, it is not meant not be a general framework. Rather, it is made especially for fine-tuning Transformer-based models available in the HuggingFace Transformers library. The Trainer also has an extension called `Seq2SeqTrainer` for encoder-decoder models, such as BART, T5 and the `EncoderDecoderModel` classes. Note that all [PyTorch example scripts](https://github.com/huggingface/transformers/tree/master/examples/pytorch) of the Transformers library make use of the Trainer.
- [HuggingFace Accelerate](https://github.com/huggingface/accelerate): Accelerate is a new project, that is made for people who still want to write their own training loop , but would like to make it work automatically irregardless of the hardware (i.e. multiple GPUs, TPU pods, mixed precision, etc.).
