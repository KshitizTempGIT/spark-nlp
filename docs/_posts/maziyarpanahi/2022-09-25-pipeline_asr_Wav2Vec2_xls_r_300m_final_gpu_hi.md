---
layout: model
title: Hindi asr_Wav2Vec2_xls_r_300m_final_gpu TFWav2Vec2ForCTC from LegolasTheElf
author: John Snow Labs
name: pipeline_asr_Wav2Vec2_xls_r_300m_final_gpu
date: 2022-09-25
tags: [wav2vec2, hi, audio, open_source, pipeline, asr]
task: Automatic Speech Recognition
language: hi
edition: Spark NLP 4.2.0
spark_version: 3.0
supported: true
annotator: PipelineModel
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained Wav2vec2  pipeline, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP.`asr_Wav2Vec2_xls_r_300m_final` is a Hindi model originally trained by LegolasTheElf.

NOTE: This pipeline only works on a CPU, if you need to use this pipeline on a GPU device please use pipeline_asr_Wav2Vec2_xls_r_300m_final

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/pipeline_asr_Wav2Vec2_xls_r_300m_final_gpu_hi_4.2.0_3.0_1664090542998.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python

pipeline = PretrainedPipeline('pipeline_asr_Wav2Vec2_xls_r_300m_final_gpu', lang = 'hi')
annotations =  pipeline.transform(audioDF)
    
```
```scala

val pipeline = new PretrainedPipeline("pipeline_asr_Wav2Vec2_xls_r_300m_final_gpu", lang = "hi")
val annotations = pipeline.transform(audioDF)
    
```
</div>

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|pipeline_asr_Wav2Vec2_xls_r_300m_final_gpu|
|Type:|pipeline|
|Compatibility:|Spark NLP 4.2.0+|
|License:|Open Source|
|Edition:|Official|
|Language:|hi|
|Size:|1.2 GB|

## Included Models

- AudioAssembler
- Wav2Vec2ForCTC