# The Same Word, Different Meaning: Static vs. Contextual Word Representations

## **Authors**  

Group Project of: 

- **Moulkioti Sotiria** — [GitHub](https://github.com/Sotiria-Moulkioti)
- **Mylonaki Danai** — [GitHub](https://github.com/PoiLson)

for the lesson of Deep Neural Networks in DSIT.

## Main idea

**Can AI understand how the meaning of a word changes depending on its context?**

This project's idea was inspired by this [post](https://blog.dailydoseofds.com/p/the-limitation-of-static-embeddings).

As the post explains, the same English word can have several meanings depending on its surroundings.
Our target is for the model to understand the surrounding sentence in order to identify the intended meaning.

For example:

`Target word: bank`
> "She went to the *bank* to withdraw money."
> 
> "They set on the *bank* of the river."

`Target word: bright`
> "The room was *bright*".
> 
> "She is a *bright* student".

Traditional embeddings such as Word2Vec assign each word type a *single* vector representation, regardless of its context.
On the contrary, contextual models such as BERT generate representations that depend on the surrounding tokens/words.

And this raises our research question...

## Research Question

Our main research question is:

**To what extent do contextual neural representations outperform static word embeddings in identifying whether
a word has the same meaning across different sentences?**

Our primary objective is to investigate word meaning in context, rather than sentence classification or text generation.

## Dataset

We plan to use the [Word-in-Context (WiC) dataset](https://pilehvar.github.io/wic/).

The dataset consists of pairs of English sentences containing the same target word. Each pair is labeled
according to whether the target word has the same meaning in both sentences.

For example:

`Target word: bank`
> "She deposited money in the *bank*."
> 
> "The *bank* approved her loan."

**->Label: Same meaning**

> "She deposited money in the *bank*."
> 
> "They were sitting on the river *bank*."

**->Label: Different meaning**

## First Approach on Methodology

We plan to investigate several approaches, starting with simpler models and progressively introducing more advanced neural
architectures.

1. **Static Word Embeddings**

   We will first investigate traditional word embeddings, such as **Word2Vec** or **GloVe**.

   These methods represent each word using a fixed vector, irrespective of where it appears. We plan to use these representations
   to establish a baseline performance, including a context-based classifier that uses surrounding words.

2. **Recurrent Neural Networks**

   We will then investigate a **Bidirectional Long Short-Term Memory (BiLSTM)** network.

   Unlike static word representations alone, a BiLSTM processes the surrounding sequence and generates context-dependent hidden
   representations. We aim to examine whether these representations can help identify differences in word meaning across sentences

3. **Contextual Word Embeddings**

   Finally, we will investigate contextual representations obtained from a pretrained **BERT** model.

   BERT uses the Transformer architecture and self-attention mechanisms to generate representations that depend on the context of
   each word. We plan to compare its representations with those obtained from the previous approaches. Depending on the available
   time and computational resources, we may also investigate the effect of fine-tuning BERT on the selected task.

## Experimental Evaluation

We plan to evaluate the proposed approaches using the classification labels provided by the WiC dataset.

And also for quantitative evaluation, we plan to use:
- **Accuracy**: The proportion of correctly classified sentence pairs.
- **Precision and Recall**: To investigate the performance of the models on each class.
- **F1-score**: To summarize the balance between precision and recall.

We also intent to investigate how different representation methods affect classification performance. Additionally, we may
explore the learned embedding spaces through visualization techniques to better understand how context influences word representations.
