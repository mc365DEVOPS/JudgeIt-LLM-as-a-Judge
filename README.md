# JudgeIt - An Auto Evaluation Framework for Generative AI Pipelines

When building Generative AI pipelines, accuracy and reliability are paramount. Therefore, it is critical to build robust evaluation frameworks to test these pipelines. Human evaluation often takes a high degree of manual effort and is difficult to scale.

JudgeIt is an automated evaluation framework designed to accurately and efficiently evaluate various Generative AI pipelines such as RAG Evaluation, Multi-Turn Query Rewrite evaluation, Text-to-SQL Evaluation, and more.

This service allows users to run batch evaluations against a variety of Generative AI pipelines. Users can input datasets with generated text and golden text to evaluate against, and JudgeIt will use an LLM as a judge to perform similarity evaluations of these inputs.

## Features

- **Automated Evaluation**: JudgeIt automates batch evaluation processes, resulting in more efficient evaluation compared to human testers.
- **Multi-Pipeline Support**: Evaluate different types of LLM pipelines including:
  - **RAG**: evaluate generated text against golden text
  - **Multi-turn query rewritings**: evaluate rewritten queries given a multi-turn conversation
- **Customization**: Configure the evaluation process with your datasets, LLM models, and specific parameters.

## Reliability Metrics

The LLM Judges in this repository have been tested against human evaluation to validate their reliability.

1. RAG Evaluation (LLM Judge evaluated against human)

   ![RAG Evaluation Reliability](/images/rag-evaluation-reliability.png)

2. Multi-turn Query Rewrite (LLM Judge evaluated against human)

   ![Multi-turn Evaluation Reliability](/images/multi-turn-evaluation-reliability.png)

## Usage

There are three types of LLM judges available in JudgeIt:

1. **RAG Evaluation (Similarity)**: evaluate generated text against golden text and receive a binary score for similarity
2. **RAG Evaluation (Rating)**: evaluate generated text against golden text and receive a 1/2/3 rating based on degree of similarity
3. **Multi-turn evaluation**: evaluate rewritten queries given a mult-turn conversation and receive a binary score for similarity

There are two methods for spinning up JudgeIt:

1. Framework
   1. This repository contains python modules to run evaluations via cli. The Framework method takes input data in the form of excel or csv files for any of these evaluations. View the [Framework Instructions](./Framework/README.md) for more detail.
2. Service-Oriented Architecture
   1. This repository contains a REST API backend and NextJS frontend to run evaluations via a UI. The SOA method takes input data in the form of excel/csv files or single inputs for any of these evaluations. View the [REST Service Instructions](./REST-Service/README.md) and [JudgeIt App Instructions](./JudgeIt-App/README.md) for more detail.

## Installation

1. Clone the repository

   ```bash
   git clone <repository url>
   ```

2. Create a python virtual environment

   ```bash
   python3 -m venv virtual-env
   source virtual-env/bin/activate
   pip3 install -r requirements.txt
   ```

3. Select a method to spin up the JudgeIt service:
   1. Framework: Use Python modules and the cli to run evaluations locally
      1. [Framework Instructions](./Framework/README.md)
   2. Service-Oriented Architecture: first spin up a REST API backend, then spin up a NextJS frontend to run evaluations via a UI
      1. [REST Service Instructions](./REST-Service/README.md)
      2. [JudgeIt App Instructions](./JudgeIt-App/README.md)

## Contributors

- Kunal Sawarkar, Chief Data Scientist
- Shivam Solanki, Senior Advisory Data Scientist
- Anand Das, Technology Engineer
- Himadri Talukder, Senior Software Engineer
- Abhilasha Mangal, Senior Data Scientist
- Kevin Huang, Sr. ML-Ops Engineer

## License

This project is licensed under the Apache-2.0 License. See the `LICENSE` file for more details.
