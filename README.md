# VOLT-Blog-Final-Version
In this blog, I will be discussing the paper "Vocabulary Leaning via Optimal Transport for Neural Machine Translation". More specifically, I will introduce the concepts discussed in the paper at an introductory level, I will highlight the importance of the question the paper is trying to answer, discuss how it answers that question, and provide examples and benchmarks to aid the understaning of the reader.

Reading time : About 10 minutes

Paper: https://arxiv.org/pdf/2012.15671.pdf

Github: https://github.com/Jingjing-NLP/VOLT

## Introduction

At its core, the paper aims to find a way to reduce resource consumption and computational times of machine translation algorithms. A key part of translating between one language and another is taking the text in the original language and breaking down into tokens to make the translation possible. Tokens are just key elements of the text, they can be words, characters, or even subwords. A subword is just a part of a word. For instance, a sub-word for both the words "happier" and "happy" could be "happ". The set of tokens that get produced from a piece of text is called a token vocabulary. For example, a possible token vocabulary for the sentence "John kicked the soccer ball" would be {kicked,soccer,ball}. VOLT tries to optimize the creation of this token vocabulary by having a noticeable reduction in the size of the token vocabulary produced from a piece of text

VOLT has other advantages other than reducing the vocabulary size. Firstly, VOLT does not only reduce size but produces an overall better vocabulary than current methods. We will see performance metrics later that show this off. Secondly, VOLT works well on multilingual MT settings. This means that VOLT performs better on a more diverse range of languages than other methods such as Byte-Pair Encoding (BPE). Lastly, VOLT uses less resources and computational time than current prevailing methods. This is because VOLT does not require trail training when it comes to computing the optimal vocabulary. Trail training just means having to iterate through all possible vocabulary sizes to find the best vocabulary at the best size, this methodology is extremely inefficient and so its use is avoided in VOLT.

The question to now be asked is why is VOLT so important. Why do we need to reduce vocabulary size in the first place? In this next section, we will discuss the current issues with other tokenization methods and why VOLT is necessary

## Issues with current tokenization models

Most current translation models use word-level vocabularies. An issue with this is that word-level vocabularies fail when it comes to handling rare words under limited vocabulary sizes. More recent research suggests the use of character level, sub-word level, or byte level token vocabularies.  Sub-word vocabularies can be seen as a middle ground between character level encodings and byte-level encondings.
