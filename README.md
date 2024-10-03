# MeDDLO: A benchmark for Metalinguistic Disagreement Detection in LLM Output

## Overview
Evaluating large language models (LLMs) for tasks like fact extraction in support of knowledge graph construction frequently involves computing accuracy metrics using a ground truth benchmark based on a knowledge graph (KG). These evaluations assume that errors represent factual disagreements. However, human discourse frequently features *metalinguistic disagreement*, where agents differ not on facts but on the meaning of the language used to express them. Given the complexity of natural language processing and generation using LLMs, we ask:
do metalinguistic disagreements occur between LLMs and KGs? We hypothesize that metalinguistic disagreement does in fact occur between LLMs and KGs, with potential relevance for the practice of knowledge graph engineering. This repository contains work towards a benchmark for evaluating the detection of factual and metalinguistic disagreements between LLMs and KGs.

## License
MIT License.
