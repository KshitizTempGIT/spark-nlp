---
layout: model
title: Arabic BertForSequenceClassification Cased model (from Ammar-alhaj-ali)
author: John Snow Labs
name: bert_classifier_arabic_marbert_dialect_identification_city
date: 2022-09-06
tags: [ar, open_source, bert, sequence_classification, classification]
task: Text Classification
language: ar
edition: Spark NLP 4.1.0
spark_version: 3.0
supported: true
annotator: BertForSequenceClassification
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained BertForSequenceClassification model, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP. `arabic-MARBERT-dialect-identification-city` is a Arabic model originally trained by `Ammar-alhaj-ali`.

## Predicted Entities

`Riyadh`, `Fes`, `Doha`, `Beirut`, `Baghdad`, `Basra`, `Benghazi`, `Tunis`, `Algiers`, `Alexandria`, `Rabat`, `Khartoum`, `Aleppo`, `Tripoli`, `Jerusalem`, `Mosul`, `MSA`, `Jeddah`, `Aswan`, `Amman`, `Muscat`, `Salt`, `Damascus`, `Cairo`, `Sanaa`, `Sfax`

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/bert_classifier_arabic_marbert_dialect_identification_city_ar_4.1.0_3.0_1662501499473.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python
documentAssembler = DocumentAssembler() \
    .setInputCols(["text"]) \
    .setOutputCols("document")

tokenizer = Tokenizer() \
    .setInputCols("document") \
    .setOutputCol("token")

seq_classifier = BertForSequenceClassification.pretrained("bert_classifier_arabic_marbert_dialect_identification_city","ar") \
    .setInputCols(["document", "token"]) \
    .setOutputCol("class")
    
pipeline = Pipeline(stages=[documentAssembler, tokenizer, seq_classifier])

data = spark.createDataFrame([["PUT YOUR STRING HERE"]]).toDF("text")

result = pipeline.fit(data).transform(data)
```
```scala
val documentAssembler = new DocumentAssembler() 
      .setInputCols(Array("text")) 
      .setOutputCols(Array("document"))
      
val tokenizer = new Tokenizer()
    .setInputCols("document")
    .setOutputCol("token")
 
val seq_classifier = BertForSequenceClassification.pretrained("bert_classifier_arabic_marbert_dialect_identification_city","ar") 
    .setInputCols(Array("document", "token")) 
    .setOutputCol("class")
   
val pipeline = new Pipeline().setStages(Array(documentAssembler, tokenizer, seq_classifier))

val data = Seq("PUT YOUR STRING HERE").toDS.toDF("text")

val result = pipeline.fit(data).transform(data)
```
</div>

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|bert_classifier_arabic_marbert_dialect_identification_city|
|Compatibility:|Spark NLP 4.1.0+|
|License:|Open Source|
|Edition:|Official|
|Input Labels:|[document, token]|
|Output Labels:|[class]|
|Language:|ar|
|Size:|611.6 MB|
|Case sensitive:|true|
|Max sentence length:|256|

## References

- https://huggingface.co/Ammar-alhaj-ali/arabic-MARBERT-dialect-identification-city
- https://camel.abudhabi.nyu.edu/madar-shared-task-2019/