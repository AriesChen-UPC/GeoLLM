# GeoLLM
**Large Language Model for Geology**

Large language models are used to organize geology-related knowledge (geology, geophysics, geophysical logging, etc.). This version uses the [ChatGLM-6B](https://github.com/THUDM/ChatGLM-6B) base model and fine-tunes it using P-tuning.

---

### Sedimentology

Sedimentology, the study of sedimentary rocks and the processes by which they are formed, includes and is related to a large number of phenomena. Sedimentology includes the five fundamental processes defined by the term sediaentation --weathering, erosion, transportation, deposition and diagenesis.

**Datasets：**《沉积岩石学（第四版）》 朱筱敏

**Model：** ChatGLM-6B

**Fine-tuning：** P-Tuning v2

**Before fine-tuning**

```
response, history = model.chat(tokenizer, "什么是沉积岩石学？", history=[])
response

沉积岩石学是一门研究沉积岩的形成、结构和成分的学科，主要关注地球表面上不同条件下的沉积过程和岩石形成机制，包括岩浆沉积、冰川沉积、洪水沉积、海洋沉积等。沉积岩石学在地质学、地球物理学、地球化学、材料科学等领域都有广泛应用，因为沉积岩是许多自然和人工地质工程的基础，如地质勘探、矿产资源开发、土木工程、环境科学等。沉积岩石学的研究对象包括沉积岩的地质特征、成分和构造特征，以及沉积岩与地壳、岩浆和变质岩的关系。研究方法包括沉积岩分析、岩相学分析、岩浆动力学分析等。
```

**After fine-tuning**

```
response, history = model.chat(tokenizer, "什么是沉积岩石学？", history=[])
response

沉积岩石学是研究沉积岩的物质成分、结构构造、岩石类型、沉积物沉积作用和沉积物质形成环境以及沉积岩分布规律的一门科学。
```

**Error Analysis:** We meticulously refined the model by approximately 500 words from academic textbooks, subsequently applying P-Tuning v2 for optimization. Detailed control of parameters was not conducted for the time being. Given the scarcity of the training data and the fine-tuning parameters, the outcomes might exhibit some irregularities.

**Results Analysis:** It is evident that the fine-tuned model shows enhanced reliability when providing answers within specialized knowledge domains. Moving forward, we will persist in enriching our training data and optimizing our fine-tuning methodologies in order to yield superior results.

---

### TODO

1. Geophysical Exploration

2. Geophysical logging

3. Petroleum Geology

etc...

---

### Related Resources
1. [ChatGLM-6B](https://github.com/THUDM/ChatGLM-6B): ChatGLM-6B is an open bilingual language model based on General Language Model (GLM) framework, with 6.2 billion parameters. With the quantization technique, users can deploy locally on consumer-grade graphics cards (only 6GB of GPU memory is required at the INT4 quantization level)# GeoLLM
