---
id: 114    
title: "Machine Learning Tasks and Model Evaluation"
permalink: /dsblog/ml-tasks-and-model-evaluation
date: 2021-07-14
categories:
  - dsblog
tags: [DS Resources, Model Evaluation, Machine Learning Tasks, NLP Tasks, NLP Model Evaluation]
header:
  teaser:  /assets/images/dspost/dsr114-ml-tasks-and-model-evaluation.jpg
last_modified_at: 2021-06-15T15:46:43-04:00
excerpt_separator: "<!--more-->"   
author: Hari Thapliyaal   
layout: dspost-layout   
excerpt:   
author_profile: true   
share: true   
toc: true   
toc_sticky: true 
mathjax: "true"
---
![Deep Learning Tasks and Models](/assets/images/dspost/dsr114-ml-tasks-and-model-evaluation.jpg)    
    
# Machine Learning Tasks and Model Evaluation   
   
## Introduction   
Machine learning is a subject where we study how to create & evaluate machine learning models. To create these models, we need different types of data. We build models which can help us do various kinds of tasks. There are hundreds of model building techniques and researchers keep adding new techniques, and architectures as when need arises. But, the question is how do you evaluate these models which are output of the model trainings? To evaluate the performance of a model on structured data, or classification/regression/clustering models, we require one kind of metrics. But this becomes complicated when we are dealing with voice, text and audio data. How do you evaluate ten models which are responsible for translation, or locating an object in the image, transcribing voice into text, captioning an image? To solve this problem, standard databases are created and everyone needs to demonstrate the performance of their model, architecture, or approach against that dataset. But, even if you have a baseline dataset, how will you evaluate various NLP or deep learning tasks? For that GLUE, SuperGLUE benchmarks are created.


## What is BLEU Benchmark?
BLEU (Bilingual Evaluation Understudy) is a metric used to evaluate the quality of machine translation. It is based on the n-gram precision between the machine translation and the reference translation.

BLEU-1 measures the unigram precision, which is the fraction of unigrams in the machine translation that also appear in the reference translation. A BLEU-1 score of 1 means that the machine translation is a perfect match for the reference translation.

BLEU-1 is a simple and easy-to-understand metric, but it can be biased towards shorter translations. For example, a machine translation that is twice as long as the reference translation will have a lower BLEU-1 score, even if it is more accurate.

To address this, BLEU-n metrics were developed, which measure the n-gram precision for n>1. BLEU-4 is the most commonly used BLEU-n metric. A BLEU-4 score of 1 means that the machine translation is a perfect match for the reference translation. However, BLEU-4 scores are typically much lower than 1, and a score of 0.5 or higher is considered to be good.

BLEU-4 is a simple and easy-to-understand metric, but it can be biased towards shorter translations. For example, a machine translation that is twice as long as the reference translation will have a lower BLEU-4 score, even if it is more accurate.

Steps to calculate BlLEU score are as following.
1. Step1: Calculate N-gram Precision: BLEU calculates precision scores based on matching n-grams (sequences of n words) between the candidate translation and the reference translations. It computes precision scores for 1-gram (unigram), 2-gram (bigram), 3-gram, and 4-gram matches.
2. Step2: Brevity Penalty: BLEU also takes into account the length of the candidate translation compared to the reference translations. This is because shorter translations tend to have an advantage in n-gram matching, but they might not convey the full meaning of the source text. BLEU applies a brevity penalty to avoid favoring overly short translations.
3. Step3: Compute Geometric Mean: BLEU combines the precision scores of different n-gram matches using a geometric mean. This is done to give a balanced consideration to different n-gram orders. This metric helps in capturing both local and global translation quality.
4. Step4: Score Calculation: The BLEU score is calculated by multiplying the geometric mean of the n-gram precisions by the brevity penalty. The result is a value between 0 and 1, where a higher score indicates a better match between the candidate translation and the reference translations.

It's important to note that while BLEU is widely used for evaluating machine translation systems, it has some limitations. For instance, BLEU relies solely on n-gram matching and does not capture higher-level semantic or syntactic aspects of translation quality. As a result, it may not always align well with human judgments of translation quality, especially when dealing with creative or complex translations.

Despite its limitations, BLEU remains a widely used and easily computable metric for quick and automated evaluation of machine translation outputs. Researchers often combine BLEU with other metrics or use it as a starting point for evaluation, but more advanced metrics have been developed over time to address its limitations.

Advantages of using BLEU score:
- It is a simple and easy-to-understand metric.
- It is relatively insensitive to changes in word order.
- It has been shown to be effective in evaluating the performance of machine translation.

Disadvantages of using BLEU score:
- It can be biased towards shorter translations.
- It does not take into account the semantic similarity between the machine translation and the reference translation.
- It can be difficult to interpret the results of BLEU score for different tasks.

## What is GLUE Benchmark?
The **GLUE (General Language Understanding Evaluation)** benchmark is a collection of diverse natural language processing (NLP) tasks designed to evaluate and compare the performance of various machine learning models and techniques in understanding and processing human language. It serves as a standard evaluation framework for assessing the general language understanding capabilities of different models.

The GLUE benchmark was **introduced in 2018** and consists of a set of **nine different NLP tasks**, covering a wide range of language understanding tasks including sentence classification, sentence similarity, natural language inference, and question answering. Some of the tasks included in GLUE are the Stanford Sentiment Treebank, Multi-Genre Natural Language Inference, and the Recognizing Textual Entailment dataset.

The primary goal of the GLUE benchmark is to encourage the development of models that can perform well across multiple NLP tasks, thus demonstrating a more comprehensive understanding of human language. The performance of models is measured using a single metric called the GLUE score, which is computed by aggregating the performance of models on individual tasks.

The GLUE benchmark has been instrumental in advancing the field of NLP and has served as a benchmark for many state-of-the-art models, including various transformer-based architectures like BERT (Bidirectional Encoder Representations from Transformers) and RoBERTa.

It's worth noting that since the introduction of the GLUE benchmark, other benchmarks like SuperGLUE and XTREME have been developed to address some limitations and provide more challenging evaluation tasks for further advancing the state of NLP research.   
- https://gluebenchmark.com/
- https://gluebenchmark.com/leaderboard
- https://paperswithcode.com/dataset/glue

The GLUE benchmark is used by companies to evaluate the performance of their NLU models. For example, Google uses the GLUE benchmark to evaluate the performance of its BERT model. The higher the GLUE score, the better the overall performance of the model on various NLP tasks.

## What are the Tasks of GLUE Benchmark?

The current version of the GLUE benchmark includes the following 9 tasks
- CoLA: A sentence-level grammaticality task.
- SST-2: A binary sentiment classification task.
- MRPC: A sentence-pair similarity task.
- STS-B: A sentence-pair similarity task that measures the semantic relatedness of two sentences.
- QQP: A question-answering task.
- MNLI: A natural language inference task that measures whether a sentence entails another sentence.
- QNLI: A natural language inference task that measures whether a sentence entails a question.
- RTE: A natural language inference task that measures whether a sentence contradicts another sentence.
- WNLI: A word similarity task that measures the similarity between two words.

## What is SuperGLUE Benchmark?
The SuperGLUE (Super General Language Understanding Evaluation) benchmark is an enhanced version of the GLUE benchmark introduced to address its limitations and provide more challenging language understanding tasks for evaluating and comparing the performance of natural language processing (NLP) models. SuperGLUE builds upon the success of GLUE and aims to push the boundaries of NLP research further.

SuperGLUE was **introduced in 2019** as an extension of GLUE, consisting of a more diverse and difficult set of language understanding tasks. It includes a **total of eight challenging tasks**, including tasks like BoolQ (Boolean Questions), COPA (Choice of Plausible Alternatives), and RTE (Recognizing Textual Entailment), among others. These tasks are carefully designed to require more advanced reasoning and understanding abilities from models.

The primary objective of SuperGLUE is to evaluate models on a more comprehensive set of tasks that demand higher levels of language comprehension and reasoning capabilities. It provides a broader and more challenging evaluation platform to assess the progress and performance of NLP models beyond what was covered by the original GLUE benchmark.

Similar to GLUE, SuperGLUE also utilizes a single evaluation metric called the SuperGLUE score to assess model performance across the different tasks. The SuperGLUE benchmark has spurred further research and development in the field of NLP, pushing for advancements in model architectures, training techniques, and performance improvements.

SuperGLUE has become a prominent benchmark for evaluating the state-of-the-art NLP models, building on the success of GLUE and encouraging the development of more sophisticated models that can tackle complex language understanding tasks.

It's important to note that the SuperGLUE benchmark, while providing more challenging tasks, is still evolving, and researchers continue to work on expanding and refining the benchmark to further push the boundaries of NLP research.   
- https://super.gluebenchmark.com/
- https://super.gluebenchmark.com/leaderboard
- https://paperswithcode.com/dataset/superglue


## GLUE & SuperGLUE tasks

Below is list of different NLP and Deep Learning tasks for which different benchmark datasets are created and model's perormance is measured against those tasks.

Sno|Task|Corpus|Paper|GLUE|SuperGLUE
---|--- | --- | --- | --- | ---
1 | Sentence acceptability judgment | [CoLA (Corpus of Linguistic Acceptability)](https://nyu-mll.github.io/CoLA/) | [CoLA Warstadt et al., 2018](https://arxiv.org/abs/1805.12471) |Yes | No
2 | Sentiment analysis | [SST-2 (Stanford Sentiment Treebank)](https://nlp.stanford.edu/sentiment/index.html) | [SST-2 Socher et al., 2013](https://nlp.stanford.edu/~socherr/EMNLP2013_RNTN.pdf) |Yes | No
3 | Paraphrasing/sentence similarity | [MRPC (Microsoft Research Paraphrase Corpus)](https://www.microsoft.com/en-us/download/details.aspx?id=52398) | [MRPC Dolan and Brockett, 2005](https://aclanthology.org/I05-5002) |Yes | No
4 |  | [STS-B (Semantic Textual Similarity Benchmark)](http://ixa2.si.ehu.eus/stswiki/index.php/STSbenchmark) | [STS-B Ceret al., 2017](https://arxiv.org/abs/1708.00055) |Yes | No
5 |  | [QQP (Quora Question Pairs)](https://quoradata.quora.com/First-Quora-Dataset-Release-Question-Pairs) | [QQP Iyer et al., 2017](https://quoradata.quora.com/First-Quora-Dataset-Release-Question-Pairs) |Yes | No
6 | Natural language inference | [MNLI (Multi-Genre Natural Language Inference)](https://arxiv.org/abs/1704.05426) | [MNLI Williams et al., 2017](https://arxiv.org/abs/1704.05426) |Yes | No
7 |  | [QNLI (Question-answering Natural Language Inference)](https://rajpurkar.github.io/SQuAD-explorer/) | [QNLI Rajpurkar et al.,2016](https://arxiv.org/abs/1606.05250) |Yes | No
8 |  | [RTE (Recognizing Textual Entailment)](https://aclweb.org/aclwiki/Recognizing_Textual_Entailment) | [RTE Dagan et al., 2005](https://link.springer.com/chapter/10.1007/11736790_9) |Yes | Yes
9 |  | [CB (CommitmentBank)](https://github.com/mcdm/CommitmentBank) | [CB De Marneff et al., 2019](https://semanticsarchive.net/Archive/Tg3ZGI2M/Marneffe.pdf) |No | Yes
10 | Sentence completion | [COPA (Choice of Plausible Alternatives)](https://people.ict.usc.edu/~gordon/copa.html) | [COPA Roemmele et al., 2011](https://www.researchgate.net/publication/221251392_Choice_of_Plausible_Alternatives_An_Evaluation_of_Commonsense_Causal_Reasoning) |No | Yes
11 | Word sense disambiguation | [WiC (Word-in-Context)](https://pilehvar.github.io/wic/) | [WIC Pilehvar and Camacho-Collados, 2018](https://arxiv.org/abs/1808.09121) |No | Yes
12 |  | [WNLI (Winograd Natural Language Inference)](https://cs.nyu.edu/~davise/papers/WinogradSchemas/WS.html) | []() |Yes | No
13 | Question answering | [MultiRC (Multi-sentence Reading Comprehension)](https://cogcomp.org/multirc/) | [MultiRC Khashabi et al., 2018](https://aclanthology.org/N18-1023) |No | Yes
14 |  | [ReCoRD (Reading Comprehension with Commonsense Reasoning Dataset)](https://sheng-z.github.io/ReCoRD-explorer/) | [ReCoRD Zhang et al., 2018](https://arxiv.org/abs/1810.12885) |No | Yes
15 |  | [BoolQ (Boolean Questions)](https://github.com/google-research-datasets/boolean-questions) | [BoolQ Clark et al., 2019](https://arxiv.org/abs/1905.10044) |No | Yes
16 | Common Sense Reasoning | [WSC (Winograd Schema Challenge)](https://cs.nyu.edu/~davise/papers/WinogradSchemas/WS.html) | [](https://cs.nyu.edu/~davise/papers/WinogradSchemas/WS.html) |No | Yes
17 |  | [AX-b : Broadcoverage Diagnostic - Mathew's Corr]() | []() |No | Yes
18 |  | [AX-g : Winogender Shema Diagnostic Gender Parity - Accuracy]() | []() |No | Yes

### What is the difference between BLEU and GLUE

The **BLEU (Bilingual Evaluation Understudy)** score and the **GLUE (General Language Understanding Evaluation)** score are two different evaluation metrics used in the field of natural language processing (NLP), and they serve different purposes and evaluate different aspects of NLP models.

BLEU is a metric commonly used to evaluate the **quality of machine translation** systems. It measures the similarity between the machine-generated translations and reference translations provided by human translators. BLEU score is **based on n-gram precision**, where it compares the n-gram sequences (typically up to 4-grams) between the machine-generated output and the reference translations. It assigns a score between 0 and 1, with a higher score indicating better translation quality.

## What is METEOR Score?
**METEOR (Metric for Evaluation of Translation with Explicit ORdering)** is a popular automatic evaluation metric used in the field of Natural Language Processing (NLP) to assess the quality of machine translation outputs. METEOR is designed to measure the overall similarity and alignment between a generated translation and a reference (human-generated) translation, taking into account multiple levels of linguistic analysis.

Unlike simpler metrics such as BLEU (Bilingual Evaluation Understudy), which primarily focus on measuring n-gram overlaps between the generated and reference translations, METEOR incorporates more sophisticated linguistic features and alignments to provide a more comprehensive evaluation.

Key features of the METEOR metric include:

- Tokenization and Stemming: METEOR tokenizes and stems both the generated and reference translations to handle variations in word forms and improve alignment.
- Exact Matching and Stem Matching: METEOR calculates the precision and recall of exact word matches as well as matches based on stemmed forms of words, considering synonyms and related words.
- Alignment and Synonymy: METEOR uses a paraphrase database to identify synonyms and related words, which helps in capturing semantically equivalent terms.
- Word Order: METEOR explicitly considers word order and alignment between words in the generated and reference translations.
- Chunk-based Matching: METEOR evaluates matches at the chunk level, which allows for partial credit for translations that have word-level differences but still capture the same meaning.
- Punctuation and Function Words: METEOR takes into account punctuation and function words and their alignment, as they play a role in overall sentence coherence.
- Precision and Recall: METEOR calculates precision and recall scores for each of the above components and combines them to compute the final metric.
- Normalization and Penalty: METEOR applies normalization to the precision and recall scores and incorporates penalty terms to balance precision and recall contributions.

The final METEOR score is a combination of these individual components, reflecting the quality of the generated translation in terms of semantic content, syntax, word choice, and alignment with the reference translation. METEOR is designed to address some of the limitations of BLEU and provide a more holistic evaluation of translation quality, considering linguistic variations and nuances.

METEOR has been widely used in machine translation research and competitions, serving as an important tool for comparing and benchmarking different translation systems and approaches. It provides a more comprehensive and linguistically informed perspective on translation quality, making it a valuable addition to the arsenal of NLP evaluation metrics.

## What is XTREME Benchmark?
The XTREME (Cross-lingual TRansfer Evaluation of Multilingual Encoders) benchmark is a comprehensive evaluation framework **introduced in 2020** for assessing the performance of multilingual models in natural language understanding (NLU) tasks across multiple languages. It aims to evaluate the generalization and transfer capabilities of models in cross-lingual settings.

XTREME was developed as an extension of previous benchmarks like GLUE and SuperGLUE, with a specific focus on evaluating models' **abilities to understand and process languages beyond English**. It includes a diverse range of tasks spanning multiple languages, such as named entity recognition, part-of-speech tagging, machine translation, sentence classification, and question answering, among others.
Tasks on [xtreme bechmark](https://sites.research.google/xtreme)   

- Sentence-pair Classification	
- Structured Prediction	
- Question Answering	
- Sentence Retrieval

The main objective of the XTREME benchmark is to encourage the **development of models that can effectively transfer knowledge across different languages**, leveraging pretraining on large-scale multilingual data. By evaluating models on a wide range of languages and tasks, XTREME provides insights into the cross-lingual transfer capabilities and identifies areas for improvement in multilingual NLU.

Similar to GLUE and SuperGLUE, XTREME utilizes a single metric called the XTREME score to assess the performance of models across the various tasks and languages. The XTREME benchmark serves as an important evaluation platform for advancing research and development in multilingual NLU, fostering the development of models that can effectively handle language diversity and facilitate cross-lingual understanding.

XTREME has gained significant attention and has been instrumental in driving progress in multilingual NLU, pushing researchers to develop models that exhibit strong cross-lingual transfer capabilities and perform well across a wide range of languages and tasks. The benchmark continues to evolve and expand to include additional languages, tasks, and evaluation metrics to further enhance the evaluation of multilingual models.   
- https://sites.research.google/xtreme
- https://arxiv.org/abs/2003.11080
- https://paperswithcode.com/dataset/xtreme

## What is ROUGE Score? 
Recall-Oriented Understudy for Gisting Evaluation is a set of metrics for evaluating the quality of automatic summaries and machine translation. It measures the similarity between a machine-generated summary and a reference summary using overlapping n-grams, word sequences that appear in both the machine-generated summary and the reference summary.

The most common n-grams used are unigrams, bigrams, and trigrams. ROUGE score calculates the recall of n-grams in the machine-generated summary by comparing them to the reference summaries.

Formula for calculating ROUGE-N:

ROUGE-N = $$\frac{\sum_{i=1}^{m} \text{card}(S_i \cap R_i)}{\sum_{i=1}^{m} \text{card}(R_i)}$$
 
where:

$$S_i$$ is the set of n-grams in the machine-generated summary   
$$R_i$$ is the set of n-grams in the reference summary

m is the maximum n-gram length

For example, ROUGE-1 measures the overlap of unigrams, ROUGE-2 measures the overlap of bigrams, and ROUGE-L measures the longest common subsequence of the machine-generated summary and the reference summary.

Advantages of using ROUGE score:
- It is a simple and easy-to-understand metric.
- It is relatively insensitive to changes in word order.
- It has been shown to be effective in evaluating the performance of automatic summaries and machine translation.

Disadvantages of using ROUGE score:
- It does not take into account the semantic similarity between the machine-generated summary and the reference summary.
- It can be biased towards longer summaries.
- It can be difficult to interpret the results of ROUGE score for different tasks.

## What is BIG-Bench?
BIG-Bench is a collaborative benchmark intended to probe large language models and extrapolate their future capabilities. It is a diverse evaluation suite that focuses on tasks believed to be beyond the capabilities of current language models. [214 tasks](https://dasarpai.com/dsblog/nlp-tasks#214-nlp-tasks-from-big-benchmark) included in BIG-bench are summarized by keyword.

## Deep Learning Tasks & Models on Huggingface (100K Models)
There are many tasks like below for different modalities. And there are different metrics to measure the performance of a model against those tasks. In future I will expend this article, which will contain the metrics for the tasks mentioned below.

### [Computer Vision Models](https://huggingface.co/models?pipeline_tag=translation), 6000+ Models    
1 [Depth Estimation](https://huggingface.co/tasks/depth-estimation)    
2 [Image Classification](https://huggingface.co/tasks/image-classification)    
3 [Image Segmentation](https://huggingface.co/tasks/image-segmentation)    
4 [Image-to-Image](https://huggingface.co/tasks/image-to-image)    
5 [Object Detection](https://huggingface.co/tasks/object-detection)    
6 [Video Classification](https://huggingface.co/tasks/video-classification)    
7 [Unconditional Image Generation](https://huggingface.co/tasks/unconditional-image-generation)    
8 [Zero-Shot Image Classification](https://huggingface.co/tasks/zero-shot-image-classification)    
    
### [Natural Language Processing Models](https://huggingface.co/models?pipeline_tag=text-generation), 65000+ Models    
1 [Conversational](https://huggingface.co/tasks/conversational)    
2 [Fill-Mask](https://huggingface.co/tasks/fill-mask)    
3 [Question Answering](https://huggingface.co/tasks/question-answering)    
4 [Sentence Similarity](https://huggingface.co/tasks/sentence-similarity)    
5 [Summarization](https://huggingface.co/tasks/summarization)    
6 [Table Question Answering](https://huggingface.co/tasks/table-question-answering)    
7 [Text Classification](https://huggingface.co/tasks/text-classification)    
8 [Text Generation](https://huggingface.co/tasks/text-generation)    
9 [Token Classification](https://huggingface.co/tasks/token-classification)    
10 [Translation](https://huggingface.co/tasks/translation)    
11 [Zero-Shot Classification](https://huggingface.co/tasks/zero-shot-classification)    
    
### [Audio Models](https://huggingface.co/models?pipeline_tag=voice-activity-detection), 10000+ Models    
1 [Audio Classification](https://huggingface.co/tasks/audio-classification)    
2 [Audio-to-Audio](https://huggingface.co/tasks/audio-to-audio)    
3 [Automatic Speech Recognition](https://huggingface.co/tasks/automatic-speech-recognition)    
4 [Text-to-Speech](https://huggingface.co/tasks/text-to-speech)    
5 [Tabular](https://huggingface.co/models?pipeline_tag=tabular-classification)    
6 [Tabular Classification](https://huggingface.co/tasks/tabular-classification)    
7 [Tabular Regression](https://huggingface.co/tasks/tabular-regression)    
    
### [Multimodal Models](https://huggingface.co/models?pipeline_tag=reinforcement-learning), 9000+ Models    
1 [Document Question Answering](https://huggingface.co/tasks/document-question-answering)    
2 [Feature Extraction](https://huggingface.co/tasks/feature-extraction)    
3 [​Image-to-Text](https://huggingface.co/tasks/image-to-text)    
4 [Text-to-Image](https://huggingface.co/tasks/text-to-image)    
5 [Text-to-Video Contribute](https://huggingface.co/tasks/text-to-video)    
6 [Visual Question Answering](https://huggingface.co/tasks/visual-question-answering)

### [Reinforcement Learning](https://huggingface.co/tasks/reinforcement-learning), 22000+ Models