# AI, Language model and LLM

## What is Artificial Intelligence?
The term *artificial intelligence* (AI) is often used to describe computer systems dedicated to performing tasks close to human intelligence, such as speech recognition, language translation, and visual perception. It is the intelligence of software as opposed to the intelligence of humans.

Here is a more formal definition by one of the founders of the artificial intelligence discipline:

> [Artificial intelligence is] the science and engineering of making intelligent machines, especially intelligent computer programs. It is related to the similar task of using computers to understand human intelligence, but AI does not have to confine itself to methods that are biologically observable.

## What is Language AI?

Language AI refers to a subfield of AI that focuses on developing technologies capable of understanding, processing, and generating human language. The term *Language AI* can often be used interchangeably with *natural language processing* (NLP) with the continued success of machine learning methods in tackling language processing problems.

## **From Language Models to Large Language Models**

While language models have been around for a while, they’ve only been able to grow to the scale they are today with *self-supervision.* This section gives a quick overview of what language model and self-supervision mean. If you’re already familiar with those, feel free to skip this section.

## Language models
A *language model* encodes statistical information about one or more languages. Intuitively, this information tells us how likely a word is to appear in a given context. For example, given the context “My favorite color is __”, a language model that encodes English should predict “blue” more often than “car”.**

There are two main types of language models: *masked language models* and *autoregressive language models*. They differ based on what information they can use to predict a token:

*Masked language model***:  A masked language model is trained to predict missing tokens anywhere in a sequence, *using the context from both before and after the missing tokens*. In essence, a masked language model is trained to be able to fill in the blank. For example, given the context, “My favorite __ is blue”, a masked language model should predict that the blank is likely “color”. A well-known example of a masked language model is bidirectional encoder representations from transformers, or BERT ([Devlin et al., 2018](https://arxiv.org/abs/1810.04805)).**

**As of writing, masked language models are commonly used for non-generative tasks such as sentiment analysis and text classification. They are also useful for tasks requiring an understanding of the overall context, such as code debugging, where a model needs to understand both the preceding and following code to identify errors.
*Autoregressive language model*: An autoregressive language model is trained to predict the next token in a sequence, *using only the preceding tokens*. It predicts what comes next in “My favorite color is __*.*”[3](https://learning.oreilly.com/library/view/ai-engineering/9781098166298/ch01.html#id541) An autoregressive model can continually generate one token after another. Today, autoregressive language models are the models of choice for text generation, and for this reason, they are much more popular than masked language models**
