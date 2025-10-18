Sentiment Analysis of Financial Text Data from News Article Summaries from Alpha Vantage using the Huggingface transformer library.
Typical LLM Process
Usually you have some sort of "base" pre-trained model and then you fine-tune it to your specific dataset.
Pre-training: (MASSIVE TRAINING SET!)
Involves training a model on a large, generic dataset to learn broad language understanding, without focusing on specific tasks.
For ChatGPT you train on good chunk of the internet, you get an Internet document completer with undefined behavior.
Fine-tuning: (SMALL, SPECIFIC TRAINING SET!)
Adapts the pre-trained model to a specific task by training on a smaller, task-specific dataset, optimizing the model for particultar objectives.
With ChatGPT fine tune on assistant training data where question is on top and answer is below. A question-answerer in other words.
For example, in our case financial news sentiment classfication of "Bearish","Bullish", or "Neutral" would be the task.
Reinforcement Learning From Human FeedBack
Let model respond and different raters rate which response is better so can predict which candidate response is more desirable and run PPO to fine tune this sampling policy so answers that ChatGPT gives better answer with respect to reward.
Hugging Face
" 👋 Hi!

We are on a mission to democratize good machine learning, one commit at a time. "

https://huggingface.co/

Hugging Face Transformer Library
Comprehensive open-source AI library across various domains like Natural Language Processing (NLP) + Computer Vision + Audio.
It has many pre-trained an fine tuned models in its model hub. https://huggingface.co/models
It has tools for fine-tuning and building upon pre-trained models
User-friendly: Eases the creation and deployment of NLP models with PyTorch and TensorFlow integration for customization.
Versatile: Includes multilingual support and offers comprehensive tools to build upon existing models.
BERT (Bidirectional Encoder Representations from Transformers) by Google as base model
A revolutionary pre-trained language model that captures contextual relationships in text, enabling state-of-the-art performance across various natural language processing tasks
Bert Pretraining:
Masked Language Model (MLM) randomly hides some words in a sentence and trains the model to predict them based on their context
Next Sentence Prediction (NSP) involves understanding the relationship between two sentences.
Finbert
"Pre-trained BERT knew how to talk, but now it was time to teach it how to talk like a trader. We took the pre-trained BERT and then further trained it on a purely financial corpus called Reuters TRC2."
Fine-tuning with labeled data for financial sentiment classification with the Financial Phrasebank. "It is a very well thought-out and carefully labeled albeit a small dataset. Researchers extracted 4500 sentences from various news articles, which include financial terms. Then 16 experts and master students with finance backgrounds labeled them. They didn’t only report labels but also inter-annotator agreement level for each sentence, which means how many experts labelled as positive, neutral and negative." *The later Yi Yang et al released finbert-tone model "is the FinBERT model fine-tuned on 10,000 manually annotated (positive, negative, neutral) sentences from analyst reports. This model achieves superior performance on financial tone analysis task."
https://github.com/yya518/
https://huggingface.co/yiyanghkust/finbert-tone
Goal of this video
1. Do sentiment analysis on alpha-vantage dataset using pre-trained FinBert model using Transformers' Pipeline module which basically abstracts everything into:
Input: Sentence.
Output: Sentiment Score.
2. Fine-tune this model to alpha-vantage dataset using Transformers' Trainer module.
Preliminaries
Need a GPU
Installs necessary libraries then restart
