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
The actual technique of building word embeddings varies across models, although most methods may be classified as count-based or predict-based, with the latter using neural networks.
In this lesson, we'll look at Skip-gram, one of the most prominent neural word-embedding models. 
## Skip gram
The goal of skip-gram is to forecast the contexts of a given target-word.
The contexts are the target's immediate neighbors, and they are obtained via a window of variable size n — by collecting n words to the target's left and n words to its right.The model is trained using data pairs (Vt, Vc), where V is the vocabulary and t, c are indices of a target-word and one of its context-words.
The goal of the original Skip-gram is to maximize P(Vc|Vt), which is the probability of Vc being predicted as Vt's context for all training pairings. 

If we define the set of all training pairings as D, we can represent this goal as maximising the expression: 
![source](https://github.com/adrienpayong/skip-gram/blob/main/Capture1.PNG)
We'll need a way to measure the proximity of the target-word Vt and the context-word Vc in order to compute P(Vc|Vt).
This proximity is calculated in Skip-gram by taking the dot product of the target's input-embedding and the context's output-embedding.
The distinction between input-embeddings and output-embeddings is that the former represent words when they serve as a target, whilst the latter operate as contexts for other words.
Once the model has been trained, the input-embedding matrix is often employed as the final word embeddings in downstream tasks.
It is critical to understand this difference, as well as the fact that in Skip-gram, each word is connected with two unique representations.
Now, if we define uc as the measure of word proximity, E as the matrix containing input-embeddings, and O as the matrix holding output-embeddings, we get: 
![source](https://github.com/adrienpayong/skip-gram/blob/main/Capture2.PNG)
