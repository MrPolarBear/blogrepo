# Alllll Naturale Language Processing

<br>
<br>
Wow, sure is easy to calculate statistics on just numbers, I mean it just makes sense! But calculating statistics on words? H M M   sounds like nonsense. I mean, if we could just take in, let's say, a whole bunch of tweets with a targeted hashtag, and ran some nerd math function on top, you can't possibly get any meaningful results, can you??

<br>
<br>
***W o w!*** well I got a surprise for you; there IS a way to take in tweets, run a model and unlock insights hidden within the text data!. In this article we will explore how to run a Natural Language Processing (NLP) model, right from the beginning of text preprocessing steps to building and training the model.

## Yall put too much text in these tweets, we gotta make it easier for our computer buddy here
Preprocessing the text of whatever you are trying to analyze can be boiled down to these steps:
1. Tokenization:
    - This involves breaking down the text into smaller chunks, with options of each word becoming individual, or grouped up in pairs, 3's, 4's, whatever you believe will benefit your model!
        - Example: ('This phrase will be tokenized into single values) -> ('This', 'phrase', 'will', 'be', 'tokenized', 'into', 'single', 'values')
    - This step is necessary so the computer cam understand the structure and meaning of text, not try to gargle down all the text at once.
2. Lowercasing and stopword removal.
    - I put these together since I believe this needs little explaination. Lowercasing all the letters helps the machine process the data quicker, only having to worry about the base lower characters of the alphabet. Stopword removal would be the process of removing words such as 'and', 'the' and 'is'. These words provide little value, so removing them will help reduce noise for the machine model.
3. Stemming:
    - This step will reduce words down to their 'base' form by removing suffixes and prefixes. Such as the words ran, running, and runs. These would be 'stemmed' to run. This process will help reduce dimensionality and not let your computer's brain explode if you try to run a model on the whole text instead. 
4. Lemmatization:
    - Lemmy here does something a bit different than stemmy. Lemmy considers the context and part of speech of a word, then transforming words to their base of dictionary form, known as lemma. But I like lemmy better so I'll keep calling it lemmy. Unlike stemmy, lemmy will produce valid words. (Stemmy can sometimes reduce words down to nonsense to humans). If lemmy sees the word "better", that word would be lemmatized to "good".
5. Vectorization:
    - After the above 3 steps are accomplished, you can then proceed to vectorize our text. This process converts text data into numerical vectors that machine learning models can understand. Two popular ones are CountVectorizer (CV) and Term Frequency-Inverse Document Frequency (TD-IDF)
        - CV: 
            - Converts the text document to a matrix of token counts.
            - Represents each doc as a vector of term frequencies.
            - Simple and effective means of capturing occurances and distribution of terms.
        - TD-IDF
            - Calculates imprtance of a term in a document or corpus, by analyzing the frequency in the document and inverse frequency across the whole corpus
            - Assigns higher weights to terms that are frequent in the certain document but rare across the whole corpus
            - Useful for capturing uniqueness of terms

<br>
<br>
Below is an example of the whole process. Note that directly copy and pasting this will not work as it needs a proper input and I do not provide a proper input here.
<br>
<br>

### Imports
    import nltk
    from nltk.corpus import stopwords
    from nltk.stem import PorterStemmer, WordNetLemmatizer
    from sklearn.feature_extraction.text import TfidfVectorizer, CountVectorizer
    from sklearn.model_selection import train_test_split
    from sklearn.linear_model import LogisticRegression
    from sklearn.metrics import accuracy_score


### Text Preprocessing

    nltk.download('stopwords')
    nltk.download('wordnet')
    
    #This initializes the stopwords to remove, for the English language
    stop_words = set(stopwords.words('english'))

    #Initializing stemmer and lemmatizer. There are others to pick from. 
    stemmer = PorterStemmer()
    lemmatizer = WordNetLemmatizer()

    # Perform text preprocessing steps on the text data
    def preprocess_text(text):
        # Tokenization
        tokens = nltk.word_tokenize(text)

        # Case Normalization
        tokens = [token.lower() for token in tokens]

        # Stopword Removal
        tokens = [token for token in tokens if token not in stop_words]

        # Stemming and Lemmatization
        tokens = [stemmer.stem(lemmatizer.lemmatize(token)) for token in tokens]

        # Join the tokens back into a single string
        preprocessed_text = ' '.join(tokens)

        return preprocessed_text
    
### Vectorization
    # Load and preprocess the text data
    text_data = [...]  
    # List of text documents above, would be your own input here.
    preprocessed_data = [preprocess_text(text) for text in text_data]

    # Vectorize the preprocessed text using TF-IDF
    tfidf_vectorizer = TfidfVectorizer()
    tfidf_matrix = tfidf_vectorizer.fit_transform(preprocessed_data)

    # Alternatively, vectorize using CountVectorizer
    count_vectorizer = CountVectorizer()
    count_matrix = count_vectorizer.fit_transform(preprocessed_data)

### Model Training and Evalutaion using TD-IDF
    # Split the data into train and test sets
    X_train, X_test, y_train, y_test = train_test_split(tfidf_matrix, labels, test_size=0.2, random_state=42)

    # Train a logistic regression model
    model = LogisticRegression()
    model.fit(X_train, y_train)

    # Make predictions on the test set
    y_pred = model.predict(X_test)

    # Evaluate the model
    accuracy = accuracy_score(y_test, y_pred)
    print(f"Accuracy: {accuracy}")


<br>
<br>

# Conclusion:
In this guide, we covered the essential steps of text preprocessing, including stemming, lemmatization, and vectorization techniques such as TF-IDF and CountVectorizer. These techniques are crucial for preparing text data and extracting meaningful features for NLP tasks. By following the example code, you can apply these techniques to your own text data and train machine learning models for various NLP applications.
Remember that text preprocessing and vectorization are iterative processes that require experimentation and fine-tuning based on the characteristics of your data and the specific task at hand.