### Example Tutorial Markdown Page (01_Introduction.md)

# Introduction to SpaCy

In this tutorial, we'll cover the basics of setting up SpaCy and performing some fundamental NLP tasks such as tokenization.

## What is SpaCy?

SpaCy is a free, open-source library for advanced Natural Language Processing (NLP) in Python. It's designed for production use and helps you build applications that process and understand large volumes of text.

## Basic Operations with SpaCy

### Installing SpaCy

If you haven't already installed SpaCy, you can do so using pip:

```bash
pip install spacy
```

### Loading a Language Model

To perform NLP tasks, you need to load a language model. Here we use the English model:

```python
import spacy
nlp = spacy.load('en_core_web_sm')
```

### Tokenization

Tokenization is the process of breaking text into individual words, phrases, symbols, or other meaningful elements called tokens. Here's how you can tokenize a sentence:

```python
text = "SpaCy is an amazing tool!"
doc = nlp(text)
tokens = [token.text for token in doc]
print(tokens)
```

## Conclusion

You've now seen how to set up SpaCy and perform basic tokenization. As you proceed with the other tutorials, you'll explore more complex NLP tasks and features of SpaCy.

[Return to main page](../README.md)
```

This setup clearly separates the environment setup and project overview in the main README.md from the in-depth tutorial content in separate markdown files within a `tutorials` folder. This approach keeps your repository organized and user-friendly.
