Repo for the workshop on fine-tuning encoder-only models for text classification taught by [Research Computing and Data Services](https://www.it.northwestern.edu/departments/it-services-support/research/).

**[URL to work on Google Colab](https://colab.research.google.com/github/nuitrcs/fine_tuning_workshop/blob/main/fine_tuning_demo.ipynb)**

## Instructions to work on your local machine

**Unless you are already comfortable creating virtual environments and working with GPUs on your local machine, I suggest that you work on Google Colab.**

The instructions here work on a MacBook Pro (2023) with Apple M2 Max, which includes an integrated GPU. As opposed to Google Colab, Apple Silicon doesn't support CUDA, which is specific to NVIDIA GPUs. With Apple Silicon you can use GPU acceleration via Apple's Meta Performance Shaders (MPS) in PyTorch. For some reason, that didn't work using `conda install`, but it did work using `pip install`. You can create a virtual environment running these commands in your terminal (Mac):
- `conda create -n fine_tuning_workshop python=3.11.13`
- `conda activate fine_tuning_workshop`
    - `pip install torch torchvision torchaudio`
    - `pip install evaluate pandas numpy scikit-learn datasets transformers ipykernel accelerate`

## Instructions for the exercise

- Form groups of 3-4 people.
- In your group of 3-4 people, decide on a dataset and a question.
    - The dataset should be one of the ones used by [Laurer et al (2024)](https://www.cambridge.org/core/journals/political-analysis/article/less-annotating-more-classifying-addressing-the-data-scarcity-issue-of-supervised-machine-learning-with-deep-transfer-learning-and-bertnli/05BB05555241762889825B080E097C27?utm_campaign=shareaholic&utm_medium=copy_link&utm_source=bookmark), available on their [GitHub repo](https://github.com/MoritzLaurer/less-annotating-with-bert-nli), *except the manifesto stances toward protectionism (which I used for the demo)*.
    - The question should be a real research question (a small one) that you can answer during the workshop with the data available (e.g., "In which country is protectionist political speech more prevalent?​")
- Test that you can use the tools for today (Google Colab with CPU and GPU, Hugging Face models). You can do this by making sure you can run the notebook that I demoed.
- Fine-tune the model and answer your question.
    - These are some models that come from reputable organizations and are used in the social sciences literature for text classification tasks:
        - [`google-bert/bert-base-uncased`](https://huggingface.co/google-bert/bert-base-uncased) (110M parameters)
        - [`distilbert/distilbert-base-uncased`](https://huggingface.co/distilbert/distilbert-base-uncased) (67M parameters)
        - [`FacebookAI/roberta-base`](https://huggingface.co/FacebookAI/roberta-base) (125M parameters)
        - [`distilbert/distilroberta-base`](distilbert/distilroberta-base) (82.8M parameters)
        - Others that you can find if you're interested and have time!
    - In the notebook that I demoted, you'd replace `distilbert/distilbert-base-uncased` (in `MODEL_NAME = "distilbert/distilbert-base-uncased"`) for any of the models above. Make sure to include `<organization>/<model>`.
    - For fine-tuning the model, you can adapt the code that I used in the notebook that I demoed. You can also refer back to the checklist for fine-tuning a model and the key decisions when fine-tuning a model provided in the slides. I'm around for questions too!
    - To answer your research question, you may need to use the fine-tuned model in addition to other tools (e.g., descriptive statistics or data visualization).
- Present your dataset, question, fine-tuning strategy, results, and any challenges/lessons.
    - You can create slides if that's helpful, but no need to.
    - Keep the presentation short and focused on what's interesting and useful for other groups to know.
