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

## Experimental Results

The study compares Qwen3-8B, Bielik-11B and Vikhr-Nemo-12B-Instruct on selected English, Polish and Russian tasks.

### 1. Literary Text Summarization

Scores are mean human-evaluation ratings on a 1–5 scale across seven criteria: faithfulness, content coverage, coherence, clarity, linguistic quality, task alignment and tone neutrality.

| Source text | Language | Qwen3-8B | Bielik-11B | Vikhr-12B |
|---|---|---:|---:|---:|
| The Hobbit | English | 4.57 | 4.86 | 5.00 |
| Janko Muzykant | Polish | 2.86 | 4.71 | 3.29 |
| Crime and Punishment | Russian | 3.57 | 2.29 | 4.43 |

**Findings:** Bielik received the highest score among the three models for the Polish literary excerpt. Vikhr led on the Russian and English excerpts. These observations apply to the selected texts and do not establish a general ranking across languages.

### 2. Technical Text Analysis

Scores use the same seven-criterion human-evaluation framework.

| Source document | Language | Qwen3-8B | Bielik-11B | Vikhr-12B |
|---|---|---:|---:|---:|
| ICAO dangerous goods instructions | English | 3.14 | 4.85 | 3.86 |
| Hager residual-current device instructions | Polish | 3.14 | 3.43 | 2.43 |
| Borehole geophysical survey instructions | Russian | 3.00 | 3.86 | 4.00 |

**Findings:** Bielik led on the selected English and Polish technical texts, while Vikhr led on the Russian text. Clear and well-structured responses could still contain factual or terminology errors. For example, Bielik misinterpreted some requirements in the Hager document despite receiving the highest overall score among the three models.

### 3. Quantitative Task Accuracy

Each model answered 54 prompts: 18 underlying tasks presented in three languages. Task counts below include all three language versions.

| Task category | Prompts per model | Qwen3-8B accuracy (%) | Bielik-11B accuracy (%) | Vikhr-12B accuracy (%) |
|---|---:|---:|---:|---:|
| Simple | 18 | 100.00 | 83.33 | 100.00 |
| Moderate | 18 | 72.22 | 77.78 | 100.00 |
| difficult | 12 | 41.67 | 58.33 | 75.00 |
| Forecasting | 6 | 50.00 | 50.00 | 50.00 |

**Findings:** Vikhr achieved the highest accuracy on moderate and difficult tasks. Qwen and Vikhr answered all simple prompts correctly. All three models achieved 50% accuracy on the forecasting tasks.

### 4. Forecasting Error and Response Time

| Model | Accuracy (%) | Mean absolute error (MAE) | Mean absolute percentage error (MAPE, %) | Mean response time (s) |
|---|---:|---:|---:|---:|
| Qwen3-8B | 50.00 | 0.90 | 1.53 | 3.43 |
| Bielik-11B | 50.00 | 0.05 | 0.09 | 4.21 |
| Vikhr-12B | 50.00 | 2.18 | 3.74 | 4.83 |

**Findings:** Although forecasting accuracy was identical, numerical errors differed. Bielik had the lowest reported MAE and MAPE, while Qwen had the shortest mean response time in this experiment. Response times reflect the experimental setup and should not be treated as hardware-independent speed rankings.

## Limitations

- The benchmark uses a limited selection of texts and analytical tasks.
- Qualitative scores are human ratings, not accuracy percentages.
- The quantitative experiment contains 18 underlying tasks translated into three languages, rather than 54 independent task designs.
- Results describe performance in this study and should not be generalized to all tasks or deployment settings.
