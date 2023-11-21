# DevGPT MSR Mining Challenge 2024 - Team #11

Dataset and background: 

https://2024.msrconf.org/track/msr-2024-mining-challenge

DevGPT is a carefully curated database of conversations between developers and ChatGPT, obtained by tracking the mentions of ChatGPT and crawling the weblinks with the help of GraphQL. Essentially, the dataset consists of snapshots of conversations in JSON format captured at six different time periods along with timestamps, namely July 27, August 3, August 10, August 17, August 24 and August 31, 2023. [being updated constantly with some data captured in September too]. The challenge here is to parse the JSON files and analyze the developer-ChatGPT conversations to answer a few research questions in an attempt to better understand the quality of responses, efficacy of prompting techniques, capabilities of ChatGPT in programming contests and scope for improvement. 

Research Questions we intend to analyse as part of this challenge:
1. What type of assistance are programmers seeking more from ChatGPT? Define a set of classes like Algorithm Design, Debugging, Syntax help, Code Optimization and General Programming Questions and analyse what types of help are more sorted after by developers.
2. Do Developers Receive Comprehensive Answers from ChatGPT on their Initial queries, or do they often require follow-up interactions for clarity?
3. How accurately can we predict the length of a conversation with ChatGPT based on the initial prompt and context provided?

**Methodology for Q1:
Vectorization and Word Embeddings of Prompts Using GPT-2:** 
The process begins by transforming the text prompts into numerical representations. GPT-2 understands the context and semantics of words in the prompts, converting them into high-dimensional vectors (word embeddings). 

**Embedding Categories and List of Labels Using GPT-2:** 
The list of categories - Algorithm Design, Debugging, Syntax help, Code Optimization, Code completion, Roleplay, Interview Help and General Programming questions are classified by a list of words each that closely relate to that category. These categories and their associated labels are also converted into embeddings using GPT-2. This ensures that the category labels are represented in the same high-dimensional space as the prompts.

**Cosine Similarity Between Prompts and Category Label Embeddings: **
Once both prompts and category labels are transformed into embeddings, the next step is to calculate the cosine similarity between them. This step helps in understanding which category each prompt is most closely related to, based on the semantic similarity of their embeddings.

**Classification Using SVM with Linear Kernel: **
Now that we have the categories for each prompt, we then split the prompts and categories into train and test splits and apply Linear-kernel SVM classifier to test the predictions made by GPT2. Accuracy obtained on the test data sample is 74.65%


**Methodology for Q2: 

**Text Preprocessing: Custom text preprocessing is applied to the data, involving steps like lowercasing, removing punctuation, and stemming. This standardizes the text for analysis.

**Vectorization (TF-IDF): The initial queries are transformed into numerical vectors using the TF-IDF (Term Frequency-Inverse Document Frequency) vectorization method. This step is important for preparing the text for similarity analysis.

**Cosine Similarity Analysis: You use cosine similarity to measure the similarity between the initial queries and the follow-up interactions. This helps in classifying follow-ups as either related or new queries based on a set similarity threshold.

**Sentiment and Subjectivity Analysis: Utilizing TextBlob, you analyze the sentiment and subjectivity of the initial queries, providing insights into the emotional tone and objective vs. subjective nature of the queries.

**Statistical Aggregation: The data is then aggregated to calculate average sentiment, subjectivity, and the average number of related and new queries per conversation.


**Methodology for Q3:
The initial step involves converting text prompts into numerical representations. GPT-2 possesses the capability to comprehend the contextual and semantic aspects of words within the prompts, thereby transforming them into high-dimensional vectors known as word embeddings.

After obtaining numerical representations, such as word embeddings, from the GPT-2-transformed text prompts, the next step involves training a Random Forest machine learning model using these extracted features. The Random Forest model utilizes the learned numerical representations to make predictions based on the patterns and relationships present in the training data.

Employed the "SelectFromModel" technique for feature selection. Utilized this method to identify and retain the most significant features for my analysis.

Proceeded with further refinement by employing Random Search Cross-Validation (Random Search CV). This involves systematically exploring different combinations of hyperparameters for your model to find the most effective configuration.



