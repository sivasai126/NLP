### Text Preprocessing Tutorial (02_Text_Preprocessing.md)

# Text Preprocessing with SpaCy

In this tutorial, we will explore various text preprocessing techniques using SpaCy. Text preprocessing is crucial as it prepares raw text for further NLP tasks. This process often includes tokenization, lemmatization, removing stopwords, and more.

## Why Preprocess Text?

Text preprocessing is the first step in many NLP workflows. It transforms raw text into a more manageable and uniform format, improving the performance of NLP models by removing noise and irrelevant information.

## Basic Text Preprocessing Steps

### Tokenization

Tokenization splits text into individual tokens (usually words). We saw a brief example in the previous tutorial, and here’s a quick recap:

```python
import spacy
nlp = spacy.load('en_core_web_sm')
text = "Tokenization splits text into tokens."
doc = nlp(text)
tokens = [token.text for token in doc]
print(tokens)
```

### Lemmatization

Lemmatization reduces words to their base or root form. Unlike stemming, lemmatization considers the context and part of speech to convert the word to a meaningful base form.

```python
lemmas = [token.lemma_ for token in doc]
print(lemmas)
```

### Removing Stopwords

Stopwords are common words like 'and', 'the', etc., that may not add much meaning in text analysis. SpaCy provides a list of stopwords which you can use to filter your text.

```python
stopwords = spacy.lang.en.stop_words.STOP_WORDS
filtered_tokens = [token.text for token in doc if token.text not in stopwords]
print(filtered_tokens)
```

## Combining It All

Let’s put all these steps together to preprocess a sample text:

```python
text = "This is a sample sentence, showing off the stop words filtration."
doc = nlp(text)

cleaned_text = [token.lemma_ for token in doc if token.text not in stopwords]
print(cleaned_text)
```

In this example, we tokenize the text, remove stopwords, and apply lemmatization, which are typical preprocessing steps before moving to more complex tasks like sentiment analysis or entity recognition.

## Conclusion

You've now learned how to perform basic text preprocessing using SpaCy. These steps form the foundation for most NLP tasks and ensure that the data you work with is clean and normalized.

[Return to main page](../README.md)
```
