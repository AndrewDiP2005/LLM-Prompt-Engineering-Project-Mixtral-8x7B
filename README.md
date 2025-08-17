# Project: Analyzing Prompt Engineering Techniques on LLMs

This project demonstrates a systematic approach to evaluating and improving the output of Large Language Models (LLMs) through different prompt engineering techniques.

## Objective

I wanted to test how different prompting techniques affect an LLM's ability to solve a logic riddle.
I expected the initial Zero-shot technique to fail, and improved techniques to perform better.

## Methodology

* **Model:** `mistralai/Mixtral-8x7B-Instruct-v0.1`
* **Environment:** Google Colab with an NVIDIA A100 GPU
* **Evaluation Framework:** A custom 8-point rubric was used to score each response based on Factual Accuracy, Completeness, Clarity, and Conciseness.

## Results Summary

This table summarizes the performance of each prompting technique.

| Prompt Technique    | Final Score | Outcome                                        |
| :------------------ | :---------: | :--------------------------------------------- |
| Zero-Shot           |     4/8     | Incorrect answer, flawed reasoning             |
| Chain-of-Thought    |     4/8     | Incorrect answer, flawed step-by-step logic    |
| Role-Playing        |     4/8     | Incorrect answer, nonsensical reasoning        |
| **Few-Shot** |   **8/8** | **Correct answer, flawless reasoning** |

## Detailed Analysis

* **Zero-Shot:** The initial prompt resulted in an incorrect answer of 2 sisters, with the model failing to count "Mary" as a sibling.
* **Chain-of-Thought:** This technique also failed, as the model incorrectly identified the mother and uncle as siblings in its reasoning chain.
* **Role-Playing:** Assigning the model a "logician" persona resulted in a new incorrect answer of 0, demonstrating a different mode of logical failure.
* **Few-Shot:** By providing a clear example of a similar, correctly solved riddle, the model was able to replicate the reasoning pattern and arrive at the correct answer of 3 sisters.

## Conclusion


This experiment conclusively demonstrates that for complex logical tasks, advanced techniques like **Few-Shot prompting are essential** for ensuring reliable and accurate LLM performance. A simple prompt is insufficient and can lead to confident but incorrect answers.
