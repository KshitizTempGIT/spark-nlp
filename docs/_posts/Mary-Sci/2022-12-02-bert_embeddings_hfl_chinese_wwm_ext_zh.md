---
layout: model
title: Chinese BertForMaskedLM Cased model (from hfl)
author: John Snow Labs
name: bert_embeddings_hfl_chinese_wwm_ext
date: 2022-12-02
tags: [zh, open_source, bert_embeddings, bertformaskedlm]
task: Embeddings
language: zh
edition: Spark NLP 4.2.4
spark_version: 3.0
supported: true
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained BertForMaskedLM model, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP. `chinese-bert-wwm-ext` is a Chinese model originally trained by `hfl`.

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/bert_embeddings_hfl_chinese_wwm_ext_zh_4.2.4_3.0_1670020942972.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

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

bert_loaded = BertEmbeddings.pretrained("bert_embeddings_hfl_chinese_wwm_ext","zh") \
    .setInputCols(["document", "token"]) \
    .setOutputCol("embeddings") \
    .setCaseSensitive(True)
    
pipeline = Pipeline(stages=[documentAssembler, tokenizer, bert_loaded])

data = spark.createDataFrame([["I love Spark NLP"]]).toDF("text")

result = pipeline.fit(data).transform(data)
```
```scala
val documentAssembler = new DocumentAssembler() 
    .setInputCols(Array("text")) 
    .setOutputCols(Array("document"))
      
val tokenizer = new Tokenizer()
    .setInputCols("document")
    .setOutputCol("token")
 
val bert_loaded = BertEmbeddings.pretrained("bert_embeddings_hfl_chinese_wwm_ext","zh") 
    .setInputCols(Array("document", "token"))
    .setOutputCol("embeddings")
    .setCaseSensitive(True)    
   
val pipeline = new Pipeline().setStages(Array(documentAssembler, tokenizer, bert_loaded))

val data = Seq("I love Spark NLP").toDS.toDF("text")

val result = pipeline.fit(data).transform(data)
```
</div>

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|bert_embeddings_hfl_chinese_wwm_ext|
|Compatibility:|Spark NLP 4.2.4+|
|License:|Open Source|
|Edition:|Official|
|Input Labels:|[sentence, token]|
|Output Labels:|[bert]|
|Language:|zh|
|Size:|383.9 MB|
|Case sensitive:|true|

## References

- https://huggingface.co/hfl/chinese-bert-wwm-ext
- https://arxiv.org/abs/1906.08101
- https://github.com/google-research/bert
- https://github.com/ymcui/Chinese-BERT-wwm
- https://github.com/ymcui/MacBERT
- https://github.com/ymcui/Chinese-ELECTRA
- https://github.com/ymcui/Chinese-XLNet
- https://github.com/airaria/TextBrewer
- https://github.com/ymcui/HFL-Anthology
- https://arxiv.org/abs/2004.13922
- https://arxiv.org/abs/1906.08101