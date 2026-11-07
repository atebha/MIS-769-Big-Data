# HW 8: Prompt Engineering

## Overview

`HW08.ipynb` explores prompt-engineering techniques for business tasks using the instruction-tuned `google/flan-t5-base` model. It compares prompting approaches, examines where a small model succeeds or fails, and builds reusable prompt templates for a business domain.

## What it does

1. Establishes a zero-shot baseline by classifying customer reviews as positive, negative, or neutral.
2. Tests how changing the instructions and available labels affects sentiment classifications.
3. Compares zero-shot and few-shot prompting, including changes to the examples and their order.
4. Compares a direct arithmetic question with a chain-of-thought prompt.
5. Iteratively improves a prompt for extracting structured details from customer feedback.
6. Demonstrates role-based prompts and reusable email and structured-output templates.
7. Applies the prompt-template exercise to Adobe Analytics reporting, with examples based on web and mobile app analytics.
8. Includes written reflections and answers to the homework questions.

## Model and dependencies

The notebook installs `transformers` and `accelerate`, then loads `google/flan-t5-base` and its tokenizer from Hugging Face. It does not require a separate dataset file; the exercises use examples defined in the notebook. An internet connection is needed to install packages and download the model the first time.

## How to run

1. Open `HW08.ipynb` in Google Colab or a Jupyter environment with Python.
2. Run the setup cell to install the dependencies and load the model. The first run may take a few minutes while the model downloads.
3. Run the notebook from top to bottom so the model and prompt functions are defined before use.
4. Review the saved outputs and written reflections. Some experiments invite changes to prompts or generation settings; rerun those cells after editing to compare results.

## Key findings

- In the recorded sentiment experiment, zero-shot and few-shot prompting each classified 4 of 6 reviews correctly; the neutral reviews were a challenge.
- For the structured-feedback task, the notebook's response to Q1 identifies the worked example in version 4 as the most effective change: the output skeleton alone in version 3 did not produce the desired fields, while adding a worked example improved the response.
- The domain playground applies the prompt-library approach to Adobe Analytics reporting, a setting where results should be checked against the underlying report data.

## Limitations

- `flan-t5-base` is a relatively small model. It can miss sentiment nuance, arithmetic, or requested output details, even when the prompt is carefully structured.
- The examples and evaluation sets are small and task-specific, so the results do not establish that one prompting technique will work best for other models or business tasks.
- Generated analytics explanations are illustrative and should not be treated as verified conclusions without checking the source data.
- The notebook contains experiments that require rerunning after prompt or sampling changes; saved outputs may not reflect a later edit.

## Tools

Python, Jupyter/Google Colab, Hugging Face Transformers, Accelerate, and the `google/flan-t5-base` model.
