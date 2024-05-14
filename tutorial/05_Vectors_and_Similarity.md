### Word Vectors and Text Similarity Tutorial (05_Vectors_and_Similarity.md)


# Word Vectors and Text Similarity with SpaCy

In this tutorial, we'll explore how to work with word vectors and calculate text similarity using SpaCy. Word vectors are dense numerical representations of words in a high-dimensional space, which capture semantic meaning and relationships between words.

## Word Vectors in SpaCy

SpaCy provides access to pre-trained word vectors, which you can use directly or fine-tune for your specific tasks. Here's how to access word vectors for individual tokens:

```python
import spacy

nlp = spacy.load("en_core_web_sm")
doc = nlp("apple orange banana")

for token in doc:
    print(token.text, token.vector[:3])  # Print the first three elements of each word's vector
```

## Calculating Text Similarity

Text similarity measures the degree of closeness or similarity between two pieces of text. SpaCy allows you to calculate similarity between documents based on their word vectors:

```python
doc1 = nlp("cat")
doc2 = nlp("dog")

similarity = doc1.similarity(doc2)
print("Similarity between 'cat' and 'dog':", similarity)
```

## Visualizing Word Vectors

While word vectors are high-dimensional, you can visualize them in a lower-dimensional space using dimensionality reduction techniques like t-SNE:

```python
import spacy
import numpy as np
import matplotlib.pyplot as plt
from sklearn.manifold import TSNE

# Load the Spacy model
nlp = spacy.load("en_core_web_sm")

# Collect word vectors
words = ["apple", "orange", "banana", "dog", "cat", "elephant"]
word_vectors = np.array([nlp(word).vector for word in words])

# Apply t-SNE for dimensionality reduction
# Set perplexity to a value less than the number of samples, e.g., 5
tsne = TSNE(n_components=2, random_state=42, perplexity=5)
word_vectors_2d = tsne.fit_transform(word_vectors)

# Plot
plt.figure(figsize=(8, 6))
for i, word in enumerate(words):
    plt.scatter(word_vectors_2d[i, 0], word_vectors_2d[i, 1], marker='o', color='blue')
    plt.text(word_vectors_2d[i, 0] + 0.05, word_vectors_2d[i, 1] + 0.05, word, fontsize=12)
plt.xlabel("Dimension 1")
plt.ylabel("Dimension 2")
plt.title("Word Vectors Visualization")
plt.grid(True)
plt.show()
```

## Conclusion

You've now learned how to work with word vectors and calculate text similarity using SpaCy. These techniques are fundamental for many NLP tasks, including information retrieval, text classification, and recommendation systems.

[Return to main page](../README.md)
