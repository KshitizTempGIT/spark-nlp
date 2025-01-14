---
layout: model
title: English BertForSequenceClassification Cased model (from vaariis)
author: John Snow Labs
name: bert_classifier_extreme_go_emotion
date: 2022-09-19
tags: [bert, sequence_classification, classification, open_source, en]
task: Text Classification
language: en
edition: Spark NLP 4.1.0
spark_version: 3.0
supported: true
annotator: BertForSequenceClassification
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained BertForSequenceClassification model, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP. `extreme-go-emotion` is a English model originally trained by `vaariis`.

## Predicted Entities

`optimism 🤞`, `disappointment 😞`, `amusement 😂`, `desire 😍`, `nervousness 😬`, `sadness 😞`, `surprise 😲`, `love ❤️`, `approval 👍`, `confusion 😕`, `embarrassment 😳`, `curiosity 🤔`, `grief 😢`, `disapproval 👎`, `gratitude 🙏`, `disgust 🤮`, `excitement 🤩`, `realization 💡`, `anger 😡`, `remorse 😞`, `admiration 👏`, `caring 🤗`, `fear 😨`, `annoyance 😒`, `joy 😃`, `neutral 😐`, `relief 😅`, `pride 😌`

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/bert_classifier_extreme_go_emotion_en_4.1.0_3.0_1663608356874.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python
documentAssembler = DocumentAssembler() \
        .setInputCol("text") \
        .setOutputCol("document")

tokenizer = Tokenizer() \
    .setInputCols("document") \
    .setOutputCol("token")

sequenceClassifier_loaded = BertForSequenceClassification.pretrained("bert_classifier_extreme_go_emotion","en") \
    .setInputCols(["document", "token"]) \
    .setOutputCol("class")

pipeline = Pipeline(stages=[documentAssembler, tokenizer,sequenceClassifier_loaded])

data = spark.createDataFrame([["PUT YOUR STRING HERE"]]).toDF("text")

result = pipeline.fit(data).transform(data)
```
```scala
val documentAssembler = new DocumentAssembler() 
          .setInputCol("text") 
          .setOutputCol("document")

val tokenizer = new Tokenizer() 
    .setInputCols(Array("document"))
    .setOutputCol("token")

val sequenceClassifier_loaded = BertForSequenceClassification.pretrained("bert_classifier_extreme_go_emotion","en") 
    .setInputCols(Array("document", "token")) 
    .setOutputCol("class")

val pipeline = new Pipeline().setStages(Array(documentAssembler, tokenizer,sequenceClassifier_loaded))

val data = Seq("PUT YOUR STRING HERE").toDF("text")

val result = pipeline.fit(data).transform(data)
```
</div>

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|bert_classifier_extreme_go_emotion|
|Compatibility:|Spark NLP 4.1.0+|
|License:|Open Source|
|Edition:|Official|
|Input Labels:|[document, token]|
|Output Labels:|[class]|
|Language:|en|
|Size:|84.5 MB|
|Case sensitive:|true|
|Max sentence length:|256|

## References

- https://huggingface.co/vaariis/extreme-go-emotion