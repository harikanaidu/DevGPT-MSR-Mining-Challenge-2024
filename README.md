# DevGPT MSR Mining Challenge 2024

Dataset and background: 

DevGPT is a carefully curated database of conversations between developers and ChatGPT, obtained by tracking the mentions of ChatGPT and crawling the weblinks with the help of GraphQL. Essentially, the dataset consists of snapshots of conversations in JSON format captured at six different time periods along with timestamps, namely July 27, August 3, August 10, August 17, August 24 and August 31, 2023. [being updated constantly with some data captured in September too]. The challenge here is to parse the JSON files and analyze the developer-ChatGPT conversations to answer a few research questions in an attempt to better understand the quality of responses, efficacy of prompting techniques, capabilities of ChatGPT in programming contests and scope for improvement. 

Research Questions we intend to analyse as part of this challenge:
1. What type of assistance are programmers seeking more from ChatGPT? Define a set of classes like Algorithm Design, Debugging, Syntax help, Code Optimization and General Programming Questions and analyse what types of help are more sorted after by developers.
2. Do Developers Receive Comprehensive Answers from ChatGPT on their Initial queries, or do they often require follow-up interactions for clarity?
3. How accurately can we predict the length of a conversation with ChatGPT based on the initial prompt and context provided?

Methodology for Q1:


