---
layout: model
title: Turkish ElectraForSequenceClassification Base Cased model (from Izzet)
author: John Snow Labs
name: electra_classifier_qd_dialog_base_turkish
date: 2022-09-14
tags: [tr, open_source, electra, sequence_classification, classification]
task: Text Classification
language: tr
edition: Spark NLP 4.1.0
spark_version: 3.0
supported: true
annotator: BertForSequenceClassification
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained ElectraForSequenceClassification model, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP. `qd_dialog_electra-base-turkish` is a Turkish model originally trained by `Izzet`.

## Predicted Entities

`NQ`, `Q`

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/electra_classifier_qd_dialog_base_turkish_tr_4.1.0_3.0_1663180188207.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

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

seq_classifier = BertForSequenceClassification.pretrained("electra_classifier_qd_dialog_base_turkish","tr") \
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
 
val seq_classifier = BertForSequenceClassification.pretrained("electra_classifier_qd_dialog_base_turkish","tr") 
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
|Model Name:|electra_classifier_qd_dialog_base_turkish|
|Compatibility:|Spark NLP 4.1.0+|
|License:|Open Source|
|Edition:|Official|
|Input Labels:|[document, token]|
|Output Labels:|[class]|
|Language:|tr|
|Size:|415.1 MB|
|Case sensitive:|true|
|Max sentence length:|256|

## References

- https://huggingface.co/Izzet/qd_dialog_electra-base-turkish
- https://github.com/izzetkalic/botcuk-dataset-analyze/tree/main/datasets/qd-dialog