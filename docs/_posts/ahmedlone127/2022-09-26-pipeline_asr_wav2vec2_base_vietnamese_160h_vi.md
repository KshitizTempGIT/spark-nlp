---
layout: model
title: Vietnamese asr_wav2vec2_base_vietnamese_160h TFWav2Vec2ForCTC from khanhld
author: John Snow Labs
name: pipeline_asr_wav2vec2_base_vietnamese_160h
date: 2022-09-26
tags: [wav2vec2, vi, audio, open_source, pipeline, asr]
task: Automatic Speech Recognition
language: vi
edition: Spark NLP 4.2.0
spark_version: 3.0
supported: true
annotator: PipelineModel
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained Wav2vec2  pipeline, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP.`asr_wav2vec2_base_vietnamese_160h` is a Vietnamese model originally trained by khanhld.

NOTE: This pipeline only works on a CPU, if you need to use this pipeline on a GPU device please use pipeline_asr_wav2vec2_base_vietnamese_160h_gpu

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/pipeline_asr_wav2vec2_base_vietnamese_160h_vi_4.2.0_3.0_1664195395396.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python

    pipeline = PretrainedPipeline('pipeline_asr_wav2vec2_base_vietnamese_160h', lang = 'vi')
    annotations =  pipeline.transform(audioDF)
    
```
```scala

    val pipeline = new PretrainedPipeline("pipeline_asr_wav2vec2_base_vietnamese_160h", lang = "vi")
    val annotations = pipeline.transform(audioDF)
    
```
</div>

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|pipeline_asr_wav2vec2_base_vietnamese_160h|
|Type:|pipeline|
|Compatibility:|Spark NLP 4.2.0+|
|License:|Open Source|
|Edition:|Official|
|Language:|vi|
|Size:|349.5 MB|

## Included Models

- AudioAssembler
- Wav2Vec2ForCTC