## Word Cloud


A word cloud is a visual representation of text data where the size of each word indicates its frequency or importance.
Word clouds are widely used in NLP to quickly identify prominent words in a corpus or dataset.







## Step-by-Step Implementation

### Step 1: Text Cleaning and Preprocessing

Here we clean the raw text by removing unwanted characters, citations and symbols to prepare it for tokenisation and further NLP tasks.

Removes references like [25] and [f] from the text.
Eliminates unnecessary symbols such as closing brackets.
Produces a clean and readable version of the corpus for further processing.

from nltk.tokenize import word_tokenize, sent_tokenize
from nltk.corpus import stopwords

corpus = '''India, officially the Republic of India (Hindi: Bhārat Gaṇarājya),[25] is a country in South Asia. It is the seventh-largest country by area, the second-most populous country, and the most populous democracy in the world. Bounded by the Indian Ocean on the south, the Arabian Sea on the southwest, and the Bay of Bengal on the southeast, it shares land borders with Pakistan to the west;[f] China, Nepal, and Bhutan to the north; and Bangladesh and Myanmar to the east. In the Indian Ocean, India is in the vicinity of Sri Lanka and the Maldives; its Andaman and Nicobar Islands share a maritime border with Thailand, Myanmar, and Indonesia.'''

corpus = corpus.replace("[25]", "")
corpus = corpus.replace("[f]", "")
corpus = corpus.replace(")", "")

print(corpus)
Output:

India, officially the Republic of India (Hindi: Bhārat Gaṇarājya, is a country in South Asia. It is the seventh-largest country by area, the second-most populous country, and the most populous democracy in the world. Bounded by the Indian Ocean on the south, the Arabian Sea on the southwest, and the Bay of Bengal on the southeast, it shares land borders with Pakistan to the west; China, Nepal, and Bhutan to the north; and Bangladesh and Myanmar to the east. In the Indian Ocean, India is in the vicinity of Sri Lanka and the Maldives; its Andaman and Nicobar Islands share a maritime border with Thailand, Myanmar, and Indonesia.

### Step 2: Stop Words Removal

In this step we removes common stop words and very short words from the text to focus on meaningful terms for visualization.

Tokenizes the corpus into individual words using word_tokenize.
Filters out common English stop words like “the”, “is”, “and” etc.
Ignores very short words (length < 2) to retain only significant words for the word cloud.

import nltk
nltk.download('punkt_tab')
nltk.download('stopwords')
words = []
for word in word_tokenize(corpus):
    if (word.lower() not in stopwords.words('english')) and (len(word) >= 2):
        words.append(word.lower())
Output:

<img width="1022" height="179" alt="image" src="https://github.com/user-attachments/assets/e16e04f7-aec0-4f21-bb84-38ece03f410c" />



### Step 3: Creating Vocabulary

Here we builds a vocabulary of unique words from the cleaned corpus, which helps in analyzing word frequency and generating the word cloud.

Converts the list of words into a set to remove duplicates.
Converts the set back to a list to get the final vocabulary.
Displays the size of the vocabulary and a few sample words.


<img width="937" height="259" alt="image" src="https://github.com/user-attachments/assets/2bf963d6-0620-45a6-b76e-db13d9560fe8" />



### Step 4: Creating Encoders and Decoders

In this step we assigns a unique number to each word in the vocabulary, allowing easy mapping between words and numeric representations.


word_to_num dictionary maps each word to a unique number (encoding).
num_to_word dictionary maps each number back to its corresponding word (decoding).

num = 1
word_to_num = {}
num_to_word = {}

for word in vocab:
    word_to_num[word] = num
    num_to_word[num] = word
    num += 1

print("Word-to-Number for 'world':", word_to_num['world'])  
print("Number-to-Word for 24:", num_to_word[44])

print("Complete Word-to-Number Mapping:")
for word, number in word_to_num.items():
    print(f"{word}: {number}")


    
Output:
<img width="753" height="684" alt="image" src="https://github.com/user-attachments/assets/3b44857a-ec09-449d-9fcc-51f108a1b4ab" />
