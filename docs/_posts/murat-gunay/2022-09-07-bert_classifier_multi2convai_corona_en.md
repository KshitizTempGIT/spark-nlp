---
layout: model
title: English BertForSequenceClassification Cased model (from inovex)
author: John Snow Labs
name: bert_classifier_multi2convai_corona
date: 2022-09-07
tags: [en, open_source, bert, sequence_classification, classification]
task: Text Classification
language: en
edition: Spark NLP 4.1.0
spark_version: 3.0
supported: true
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained BertForSequenceClassification model, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP. `multi2convai-corona-en-bert` is a English model originally trained by `inovex`.

## Predicted Entities

`corona.definition`, `neo.age`, `corona.infect`, `corona.event`, `corona.protect`, `corona.ibuprofen`, `corona.travel`, `neo.hello`, `neo.joke`, `corona.test`, `neo.help`, `corona.quarantine`, `corona.leisure`, `neo.home`, `corona.rumors`, `corona.masks`, `corona.notbetreuung`, `corona.warn-app`, `corona.contact`, `corona.package`, `corona.vaccine`, `corona.course`, `undefined`, `corona.supplies`, `corona.traffic`, `corona.risk`, `corona.fahrradpruefung`, `neo.feeling`, `corona.patients`, `neo.report`, `neo.sucks`, `neo.yes`, `neo.thanks`, `corona.illness`, `neo.wyd`, `neo.sorry`, `regio.taxes.help`, `corona.symptoms`, `neo.introduce`, `neo.no`, `corona.deathRate`

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/bert_classifier_multi2convai_corona_en_4.1.0_3.0_1662513686496.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

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

seq_classifier = BertForSequenceClassification.pretrained("bert_classifier_multi2convai_corona","en") \
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
 
val seq_classifier = BertForSequenceClassification.pretrained("bert_classifier_multi2convai_corona","en") 
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
|Model Name:|bert_classifier_multi2convai_corona|
|Compatibility:|Spark NLP 4.1.0+|
|License:|Open Source|
|Edition:|Official|
|Input Labels:|[document, token]|
|Output Labels:|[class]|
|Language:|en|
|Size:|406.7 MB|
|Case sensitive:|true|
|Max sentence length:|256|

## References

- https://huggingface.co/inovex/multi2convai-corona-en-bert
- https://multi2convai/en/blog/use-cases
- https://github.com/inovex/multi2convai