This tutorial will explain how to use SpaCy for identifying named entities in text, which is a common task in NLP for extracting information about people, places, organizations, and more. Here’s how you might set up the tutorial markdown.

### Named Entity Recognition Tutorial (04_NER.md)

# Named Entity Recognition with SpaCy

In this tutorial, we'll explore how to use SpaCy for Named Entity Recognition (NER), an essential task for extracting information such as names, places, and dates from text. Understanding how to extract these entities can be crucial for many applications, including information retrieval, content summarization, and data extraction.

## What is Named Entity Recognition?

Named Entity Recognition (NER) is the process of identifying and classifying key information (entities) in text into predefined categories. This can include names of people, organizations, locations, expressions of times, quantities, monetary values, percentages, etc.

## Using SpaCy for NER

SpaCy provides an easy way to perform NER using its pre-trained models. Here's how you can use it:

```python
import spacy

# Load the pre-trained model
nlp = spacy.load("en_core_web_sm")

# Process a text
text = "Apple is looking at buying U.K. startup for $1 billion."
doc = nlp(text)

# Extract entities
entities = [(ent.text, ent.label_) for ent in doc.ents]
print(entities)
```

## Visualizing Entities

SpaCy also includes a tool for visually highlighting named entities in text, which can be very helpful for quickly identifying and verifying entities:

```python
from spacy import displacy

displacy.render(doc, style="ent", jupyter=True)  # Use jupyter=False if not in a Jupyter notebook
```

## Handling Multiple Languages

SpaCy supports multiple languages, and you can use specific models tailored for different languages. Just be sure to download the appropriate model for your language, for example, `fr_core_news_sm` for French.

## Advanced NER with SpaCy

For more advanced usage, you might want to train your NER model or fine-tune existing models. SpaCy provides comprehensive documentation and tools to help with training your custom models tailored to your specific needs.

## Conclusion

This tutorial covered the basics of performing Named Entity Recognition using SpaCy. You've learned how to extract and visualize named entities in text. This knowledge will serve as a foundation for more advanced NLP tasks such as relationship extraction and information extraction.

[Return to main page](../README.md)

