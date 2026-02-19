# N-gram is a contiguous sequence of 'N' items like words or characters from text or speech.

The items can be letters, words or base pairs according to the application. The value of ’N’ determines the order of the N-gram. 
They are fundamental concept used in various NLP tasks such as language modeling, text classification, machine translation and more.

## N-grams can be of various types based on the value of 'n':

Unigrams (1-grams) are single words

Bigrams (2-grams) are pairs of consecutive words

Trigrams (3-grams) are triplets of consecutive words

<img width="1019" height="508" alt="image" src="https://github.com/user-attachments/assets/b3c9595a-7fb4-46b3-8a31-c59db0f0017a" />

<img width="1237" height="519" alt="image" src="https://github.com/user-attachments/assets/b2dd0e54-121d-4110-9564-8d30b98177cb" />


<img width="1227" height="741" alt="image" src="https://github.com/user-attachments/assets/541774f1-4265-4fd4-ac4e-0f7859ecb416" />

<img width="1261" height="735" alt="image" src="https://github.com/user-attachments/assets/743c6ba6-a367-4e00-9fe5-e60dc1457ce1" />

<img width="1255" height="687" alt="image" src="https://github.com/user-attachments/assets/4ccacfa2-0ff8-4907-920e-7bce01484f4a" />

<img width="1245" height="708" alt="image" src="https://github.com/user-attachments/assets/0ea71c41-7234-43eb-90b6-19f4cd90572c" />

## Applications of N-grams
Language Modelling: They predict the next word in a sentence based on the previous words helping generate relevant text in tasks like text generation, chatbots and autocomplete systems.

Text Prediction: In predictive typing they suggest the next word based on recent input, improving typing speed and user experience in apps like mobile keyboards and messaging tools.

Sentiment and Text Classification: N-grams capture word sequences to classify text into categories or sentiments making it easier to identify tone and topics like sports or politics.

Plagiarism Detection: By comparing N-grams in documents systems can spot similar patterns helping detect copied or reworded content.

Speech Recognition: In speech-to-text systems they predict the next word hence enhancing transcription accuracy with contextually correct sequences.



## Advantages of N-grams in NLP
Simple and Easy to Implement: They are simple to understand and implement and they require minimal computational resources. They are suitable for baseline modeling and quick prototyping.

Low Computational Overhead: They are computationally lightweight and easy to scale when compared to neural approaches which makes them suitable for systems with limited processing power or for tasks which require rapid prototyping.

Preservation of Local Word Order: They capture short-range dependencies between words by preserving their immediate sequence which is beneficial in modeling syntactic and patterns such as negation ("not good") or phrasal constructs ("New York City").

Strong Baseline Performance: They are simple yet they often provide competitive baselines for a range of tasks including text classification, sentiment analysis, information retrieval and topic detection.


## Challenges and Limitations
Despite their benefits N-grams also has some challenges like:

Data sparsity: With larger N-grams it becomes less likely to find repeated instances of the same sequence leading to sparse data.

Lack of semantic understanding: While N-grams are good at recognizing patterns they lack the understanding of context beyond the sequences they were trained on.

Lack of long-range context: They only consider nearby words and ignore broader sentence meaning.

