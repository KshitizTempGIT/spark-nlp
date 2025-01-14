---
layout: model
title: Abkhazian asr_xls_r_ab_test_by_hf_test TFWav2Vec2ForCTC from hf-test
author: John Snow Labs
name: asr_xls_r_ab_test_by_hf_test
date: 2022-09-24
tags: [wav2vec2, ab, audio, open_source, asr]
task: Automatic Speech Recognition
language: ab
edition: Spark NLP 4.2.0
spark_version: 3.0
supported: true
annotator: Wav2Vec2ForCTC
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained Wav2vec2  model, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP.`asr_xls_r_ab_test_by_hf_test` is a Abkhazian model originally trained by hf-test.

NOTE: This model only works on a CPU, if you need to use this model on a GPU device please use asr_xls_r_ab_test_by_hf_test_gpu

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/asr_xls_r_ab_test_by_hf_test_ab_4.2.0_3.0_1664021515457.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python

audio_assembler = AudioAssembler() \
    .setInputCol("audio_content") \
    .setOutputCol("audio_assembler")

speech_to_text = Wav2Vec2ForCTC \
    .pretrained("asr_xls_r_ab_test_by_hf_test", "ab")\
    .setInputCols("audio_assembler") \
    .setOutputCol("text")

pipeline = Pipeline(stages=[
  audio_assembler,
  speech_to_text,
])

pipelineModel = pipeline.fit(audioDf)

pipelineDF = pipelineModel.transform(audioDf)
```
```scala

val audioAssembler = new AudioAssembler()
    .setInputCol("audio_content") 
    .setOutputCol("audio_assembler")

val speechToText = Wav2Vec2ForCTC
    .pretrained("asr_xls_r_ab_test_by_hf_test", "ab")
    .setInputCols("audio_assembler") 
    .setOutputCol("text") 

val pipeline = new Pipeline().setStages(Array(audioAssembler, speechToText))

val pipelineModel = pipeline.fit(audioDf)

val pipelineDF = pipelineModel.transform(audioDf)

```
</div>

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|asr_xls_r_ab_test_by_hf_test|
|Compatibility:|Spark NLP 4.2.0+|
|License:|Open Source|
|Edition:|Official|
|Input Labels:|[audio_assembler]|
|Output Labels:|[text]|
|Language:|ab|
|Size:|446.6 KB|