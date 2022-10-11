---
layout: model
title: Lithuanian asr_wav2vec_lite_gpu TFWav2Vec2ForCTC from seccily
author: John Snow Labs
name: pipeline_asr_wav2vec_lite_gpu
date: 2022-09-25
tags: [wav2vec2, lt, audio, open_source, pipeline, asr]
task: Automatic Speech Recognition
language: lt
edition: Spark NLP 4.2.0
spark_version: 3.0
supported: true
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained Wav2vec2  pipeline, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP.`asr_wav2vec_lite` is a Lithuanian model originally trained by seccily.

NOTE: This pipeline only works on a CPU, if you need to use this pipeline on a GPU device please use pipeline_asr_wav2vec_lite

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/pipeline_asr_wav2vec_lite_gpu_lt_4.2.0_3.0_1664101304218.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python

pipeline = PretrainedPipeline('pipeline_asr_wav2vec_lite_gpu', lang = 'lt')
annotations =  pipeline.transform(audioDF)
    
```
```scala

val pipeline = new PretrainedPipeline("pipeline_asr_wav2vec_lite_gpu", lang = "lt")
val annotations = pipeline.transform(audioDF)
    
```
</div>

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|pipeline_asr_wav2vec_lite_gpu|
|Type:|pipeline|
|Compatibility:|Spark NLP 4.2.0+|
|License:|Open Source|
|Edition:|Official|
|Language:|lt|
|Size:|1.2 GB|

## Included Models

- AudioAssembler
- Wav2Vec2ForCTC