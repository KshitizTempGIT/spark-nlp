---
layout: model
title: Indonesian asr_fine_tune_Wav2Vec2_XLS_R_300M_Indonesia_gpu TFWav2Vec2ForCTC for GPU from faraahahaha
author: John Snow Labs
name: asr_fine_tune_Wav2Vec2_XLS_R_300M_Indonesia_gpu
date: 2022-09-24
tags: [wav2vec2, id, audio, open_source, asr]
task: Automatic Speech Recognition
language: id
edition: Spark NLP 4.2.0
spark_version: 3.0
supported: true
annotator: Wav2Vec2ForCTC
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

Pretrained Wav2vec2  model, adapted from Hugging Face and curated to provide scalability and production-readiness using Spark NLP.`asr_fine_tune_Wav2Vec2_XLS_R_300M_Indonesia` is a Indonesian model originally trained by faraahahaha.

NOTE: This model only works on a GPU, if you need to use this model on a CPU device please use asr_fine_tune_Wav2Vec2_XLS_R_300M_Indonesia

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/asr_fine_tune_Wav2Vec2_XLS_R_300M_Indonesia_gpu_id_4.2.0_3.0_1664039263600.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python

audio_assembler = AudioAssembler() \
    .setInputCol("audio_content") \
    .setOutputCol("audio_assembler")

speech_to_text = Wav2Vec2ForCTC \
    .pretrained("asr_fine_tune_Wav2Vec2_XLS_R_300M_Indonesia_gpu", "id")\
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
    .pretrained("asr_fine_tune_Wav2Vec2_XLS_R_300M_Indonesia_gpu", "id")
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
|Model Name:|asr_fine_tune_Wav2Vec2_XLS_R_300M_Indonesia_gpu|
|Compatibility:|Spark NLP 4.2.0+|
|License:|Open Source|
|Edition:|Official|
|Input Labels:|[audio_assembler]|
|Output Labels:|[text]|
|Language:|id|
|Size:|1.2 GB|