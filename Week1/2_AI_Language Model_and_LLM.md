# AI, Language model and LLM

## What is Artificial Intelligence?

The term *artificial intelligence* (AI) is often used to describe computer systems dedicated to performing tasks close to human intelligence, such as speech recognition, language translation, and visual perception. It is the intelligence of software as opposed to the intelligence of humans.

Here is a more formal definition by one of the founders of the artificial intelligence discipline:

> [Artificial intelligence is] the science and engineering of making intelligent machines, especially intelligent computer programs. It is related to the similar task of using computers to understand human intelligence, but AI does not have to confine itself to methods that are biologically observable.

## What is Language AI?

Language AI refers to a subfield of AI that focuses on developing technologies capable of understanding, processing, and generating human language. The term *Language AI* can often be used interchangeably with *natural language processing* (NLP) with the continued success of machine learning methods in tackling language processing problems.

## **From Language Models to Large Language Models**

While language models have been around for a while, they’ve only been able to grow to the scale they are today with *self-supervision.* This section gives a quick overview of what language model and self-supervision mean. If you’re already familiar with those, feel free to skip this section.

Language models are capable of producing open-ended outputs, meaning they can use a fixed vocabulary to generate an infinite variety of combinations. This ability to create diverse outputs earns them the title of generative models and forms the foundation of what we call Generative AI.

## Language models

A *language model* encodes statistical information about one or more languages. Intuitively, this information tells us how likely a word is to appear in a given context. For example, given the context “My favorite color is __”, a language model that encodes English should predict “blue” more often than “car”.**

There are two main types of language models: *masked language models* and *autoregressive language models*. They differ based on what information they can use to predict a token:

*Auto-encoder language model*:  A masked language model is trained to predict missing tokens anywhere in a sequence, *using the context from both before and after the missing tokens*. In essence, a masked language model is trained to be able to fill in the blank. For example, given the context, “My favorite __ is blue”, a masked language model should predict that the blank is likely “color”. A well-known example of a masked language model is bidirectional encoder representations from transformers, or BERT ([Devlin et al., 2018](https://arxiv.org/abs/1810.04805)).

As of writing, masked language models are commonly used for non-generative tasks such as sentiment analysis and text classification. They are also useful for tasks requiring an understanding of the overall context, such as code debugging, where a model needs to understand both the preceding and following code to identify errors.

*Auto-regressive language model*: An autoregressive language model is trained to predict the next token in a sequence, *using only the preceding tokens*. It predicts what comes next in “My favorite color is __*.*”[3](https://learning.oreilly.com/library/view/ai-engineering/9781098166298/ch01.html#id541) An autoregressive model can continually generate one token after another. Today, autoregressive language models are the models of choice for text generation, and for this reason, they are much more popular than masked language models

 ![Types of LLM models](/images/Types_of_LLM_models.png)
  
Language models are capable of producing open-ended outputs, meaning they can use a fixed vocabulary to generate an infinite variety of combinations. This ability to create diverse outputs earns them the title of generative models and forms the foundation of what we call Generative AI.
Language models are capable of producing open-ended outputs, meaning they can use a fixed vocabulary to generate an infinite variety of combinations. This ability to create diverse outputs earns them the title of generative models and forms the foundation of what we call Generative AI.

You can think of a language model as a completion machine. Given a prompt, the model predicts how to complete it. For example:

*Prompt: "To be or not to be"*
*Completion: ", that is the question."*

It’s important to understand that these completions are probabilistic predictions—they are not guaranteed to be accurate. This blend of uncertainty and creativity makes language models both fascinating and occasionally frustrating to use.

Despite its simplicity, the idea of completion is incredibly powerful. Tasks like translation, summarization, coding, and even solving math problems can all be reframed as completion challenges. For instance:

*Prompt: “How do you say ‘How are you’ in French?”*
*Completion: “Comment ça va”*

Prompt:
*Question: Is this email likely spam? Here’s the email: <email content>*
*Answer: “Likely spam”*

In this way, a language model can function as a translator, spam classifier, or even a problem solver. However, completion isn’t the same as having a conversation. For example, a language model might respond to a question with another question instead of providing an answer—it simply extends the text.

## Self-Supervision: A Game Changer

Language modeling stands out among machine learning (ML) techniques because it can be trained using self-supervision. Unlike supervised learning, which relies on labeled datasets, self-supervision enables models to train without explicit human-labeled data, unlocking the potential for scalability.

*Supervised Learning: The Traditional Approach*
Supervised learning involves training ML models with labeled data. For example, to create a fraud detection model, you’d need to label transactions as “fraud” or “not fraud” and train the model to recognize patterns in the data. This approach has been instrumental in AI breakthroughs, such as the deep learning revolution kickstarted by AlexNet, which was trained on ImageNet’s million labeled images.

However, supervised learning has a major drawback—data labeling is expensive and time-intensive. For instance, labeling one million images for ImageNet costs around $50,000, and the costs skyrocket for complex tasks like medical image analysis or multilingual translations.

Self-supervised learning eliminates the need for manual labels by allowing models to infer them directly from the input data. Language modeling is a prime example. Each sequence of text provides both the context and the "labels" (the next word or token) the model needs to predict.

This approach leverages the vast amounts of text available—books, articles, blog posts, and even Reddit comments—to train models on an enormous scale. Self-supervision has enabled the development of Large Language Models (LLMs), which are capable of performing tasks that were once unimaginable.

### What Makes a Model "Large"?

The term Large Language Model (LLM) isn’t a strict scientific classification. The “large” in LLM typically refers to the number of parameters—variables within the model that are adjusted during training. Generally, the more parameters a model has, the more capable it is of learning and performing complex tasks. However, what’s considered “large” today might be deemed small tomorrow as technology continues to evolve.

## From Large Language Models to Foundation Models

Language models have unlocked incredible possibilities, but their capabilities are primarily confined to text. Humans, however, interact with the world through a rich tapestry of senses—vision, sound, touch, and more. To make AI truly effective in real-world scenarios, it needs to process data across multiple modalities.

This is where the evolution of language models takes center stage. Modern models like GPT-4V and Claude 3 go beyond text, incorporating image understanding into their capabilities. Others are even advancing to handle videos, 3D structures, protein models, and beyond. Expanding the data modalities these models can process enhances their versatility and effectiveness. As OpenAI pointed out in the GPT-4V system card (2023):

“Incorporating additional modalities (such as image inputs) into LLMs is viewed by some as a key frontier in AI research and development.”

While models like GPT-4V and Gemini are often still referred to as Large Language Models (LLMs), a more fitting term is foundation models. This term reflects both their foundational role in AI applications and their adaptability to a wide range of tasks and domains.

## The Shift from Specialized Models to Foundation Models

Foundation models represent a fundamental shift in how AI systems are designed. Historically, AI research was siloed by data modality:

Natural Language Processing (NLP): Focused on text-based tasks like translation and spam detection.
Computer Vision: Specialized in image tasks like object detection and classification.
Audio Models: Handled speech recognition (speech-to-text) and speech synthesis (text-to-speech).
Each modality required its own specialized models. However, foundation models break these silos by integrating multiple modalities.

## Enter Multimodal Models

A multimodal model is capable of processing and generating data across different modalities—text, images, and more. When a generative multimodal model can predict the next "token" (a unit of data) based on text and image inputs, it’s often referred to as a Large Multimodal Model (LMM).

For instance, a text-only language model predicts the next word based solely on previous text. In contrast, a multimodal model can consider both text and images (or other modalities) to make its predictions, vastly expanding its utility.

This shift to multimodal and foundation models marks a new era in AI research, where systems are no longer limited by a single type of input. These models are increasingly becoming the backbone of AI applications, paving the way for more dynamic, real-world solutions.

Just like language models, multimodal models need vast amounts of data to scale and achieve their impressive capabilities. Fortunately, self-supervision works for multimodal models as well. A great example is OpenAI’s approach with their language-image model, CLIP (2021).

Instead of manually labeling images, OpenAI used a variant of self-supervision known as natural language supervision. They mined (image, text) pairs that naturally co-occurred on the internet, creating a massive dataset of 400 million pairs. This dataset was 400 times larger than the iconic ImageNet, and crucially, it came at no additional manual labeling cost. This abundance of training data enabled CLIP to become the first model capable of generalizing across multiple image classification tasks without requiring further training—a major milestone in AI.

## Foundation Models- Usecases

Foundation models are general-purpose by design, enabling applications built on them to address a wide range of problems. Often, a single application can span multiple categories of use cases. For example:

A conversational bot might serve as both a virtual companion and an information aggregator.
An application could extract structured data from a PDF while also answering user queries about its content.
The versatility of foundation models makes them a cornerstone for solving diverse challenges across industries.

While the range of applications is broad, the distribution of use cases in open-source projects provides interesting insights. For instance, categories like education, data organization, and writing might appear to have a smaller share among open-source applications. However, this isn’t indicative of their popularity. Instead, it reflects the fact that many of these applications are tailored for enterprise use cases and thus remain proprietary.
![LLM_Application_category](/images/LLM_Application_category.png)

This adaptability and scalability demonstrate why foundation models are setting the stage for the next wave of AI-driven innovation across domains.

In the enterprise world, minimizing risk is often a top priority when adopting new technologies. According to the 2024 a16z Growth report, companies are more inclined to deploy internal-facing applications (such as knowledge management tools) over external-facing ones (like customer support chatbots). This trend highlights a cautious approach, as internal applications offer a safer environment to build AI expertise while mitigating risks tied to data privacy, compliance, and potential failures.

![LLM adoption in Enterprises](/images/LLM_adoption_in_Enterprises.png)

Even with the flexibility of foundation models, many applications built on them lean toward close-ended tasks like classification. Why? Close-ended tasks are inherently easier to evaluate, making their risks more predictable and manageable. This predictability provides a sense of control, which is especially valuable in enterprise environments where reliability is critical.

By starting with lower-risk applications, organizations can gradually build confidence in their AI capabilities, paving the way for more ambitious projects in the future
