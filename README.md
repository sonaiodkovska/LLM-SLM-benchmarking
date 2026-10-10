# LLM-SLM-benchmarking

This repository contains Python notebooks developed for my master’s thesis at SGH Warsaw School of Economics.

The research compares a multilingual model with language-specific models, exploring their performance on tasks in English, Polish and Russian.

Research Objectives

* Compare model responses across languages and task types.
* Examine performance on text summarization and numerical reasoning tasks.
* Identify strengths, limitations and differences between the evaluated models.

Models

The notebooks currently included in this repository contain experiments with:

* Bielik — a Polish language model.
* Qwen - a Russian language model.
* Qwen — a multilingual language model.

Model identifiers and configurations are specified in the notebooks.

Repository Contents

* Bielik11B.ipynb — experiments with the 11B Bielik model.
* Qwen.ipynb — experiments with Qwen.
* Vikhr_2.ipynb - experiments with Vikhr model.

The notebooks include model loading, prompt preparation, inference and experimental outputs.

Technologies

Python, Jupyter notebooks, Hugging Face Transformers, PyTorch and pandas.

Some experiments use GPU acceleration and quantization to reduce memory requirements.

Running the Notebooks

1. Open a notebook in Google Colab, Kaggle or a compatible Jupyter environment.
2. Review the installation cells and model configuration.
3. Enable GPU acceleration where required.
4. Provide any input files referenced by the notebook and update their paths.
5. Run the cells in order, following the notebook’s setup instructions.

Hardware requirements depend on the model and loading configuration. Any required Hugging Face authentication should be configured separately; access tokens should not be stored in the notebook.

Scope and Limitations

These notebooks document thesis experiments rather than a production application.

The experiments use selected tasks and texts. Findings should be interpreted within this scope, rather than as a comprehensive ranking of the models.

Author

Sofiya Iadkouskaya

## Results

| Model | Task | Language | Metric | Result |
|---|---|---|---|---|
| Bielik | Summarization | Polish | — | — |
| Qwen | Summarization | Polish | — | — |
| Bielik | Numerical reasoning | Polish | Accuracy (%) | — |
| Qwen | Numerical reasoning | Polish | Accuracy (%) | — |
