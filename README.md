# News Article Summarization

This project employed large-scale summarization dataset for Indonesia, sourced from the Liputan6.com which has been used in the Koto et al. (2020) research. Liputan6.com  covers various topics and events that happened primarily in Indonesia. The dataset incorporates online news over a 10 year period, ranging from October 2000 to October 2010.

More about the dataset: https://huggingface.co/datasets/fajrikoto/id_liputan6

## Model Metrics:
- rouge1: unigram (1-gram) based scoring
- rouge2: bigram (2-gram) based scoring
- rougeL: Longest common subsequence based scoring.
- rougeLSum: splits text using "\n"

More about the metrics: https://huggingface.co/spaces/evaluate-metric/rouge

## Project Structure
1. **Data Preparation**

   Covers combining array of sentences into one sentence for each "clean_article" and "clean_summary".
2. **Exploratory Data Analysis**

   Conduct thorough analysis of the content in both articles and their summaries to understand their structure, distribution, and key features.
3. **Data Preprocessing**

   Process of text cleaning.
4. **Fine Tuning**

   Fine tuning encoder decoder models for abstractive text summarization.

## Result

![alt text](https://github.com/andreanstev/News_Article_Summarization/blob/main/image/ROUGE-1%2C%20ROUGE-2%2C%20ROUGE-L%20and%20ROUGE-Lsum.png?raw=true)

## Conclusion

- BERT2BERT produce highest ROUGE metrics than BERT2GPT. This may be caused by the limitation of training data size, where only 3000 articles used for fine tuning. GPT generates text sequentially and relies on understanding long-range dependencies in text. It needs more data to train effectively as it must capture broader contexts and dependencies across longer sequences.

- T5 produce lower ROUGE than BERT encoder and its decoder pair. This may be caused by how well the original fine tuned model created before (the ROUGE-1 of the T5 model before fine tuned only reach 0.0287 when evaluated with test data).
