# skip-gram
The recent developments in machine learning and the increasing availability of data have had a significant influence on the area of Natural Language Processing (NLP).
They aided in the creation of novel neural architectures, resulting in significant gains in various NLP applications such as machine translation and text categorization.
One significant accomplishment is the creation of models that provide high-quality, machine-readable representations of word meanings.
These representations, also known as word embeddings, are vectors that may be employed as features in neural networks that analyze text input.
The primary goal of this tutorial is to give (1) an intelligible description of Skip-gram — a well-known model for constructing word embeddings — as well as (2) a guide for training your own embeddings and utilizing them as input in a basic neural model. 
## A little history

Unlike classic NLP techniques that correlate words with discrete representations, vector space models of meaning embed each word in a continuous vector space where words may be readily compared for similarity.
They are founded on the distributional hypothesis, which states that the meaning of a word may be deduced from the contexts in which it occurs.
Words are represented by their neighbors, according to this theory – each word is connected with a vector that encodes information about its co-occurrence with other words in the lexicon.
Lemon, for example, might be characterized using words like juice, zest, curd, or squeeze, indicating that it is a sort of fruit.
Representations constructed in this manner have a helpful property: vectors of words with similar meanings are comparable — they are near to one another in the learnt vector space.
The cosine of the angle between the vectors is a popular means of assessing this similarity. 
