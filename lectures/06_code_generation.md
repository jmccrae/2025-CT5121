# Code Generation

---

## Introduction

- Code generation uses techniques studied so far such as fine-tuning, retrieval-augmented generation, and large-scale language models.
- We will look at 4 systems:
    - [StarCoder](https://arxiv.org/abs/2305.06161)
    - [REDCODER](https://arxiv.org/abs/2108.11601)
    - [Yu et al.'s evaluation of ChatGPT](https://arxiv.org/abs/2405.12641)
    - [CodeBLEU](https://arxiv.org/abs/2009.10297)

---

## StarCoder

- Open-access Code LLM by BigCode.  
- 15.5B parameters
- 8K context length.  
- Trained on 1T tokens from GitHub’s permissive code.  
- Supports 80+ programming languages.

---

## StarCoder Architecture

- Pretrained version before fine-tuning.  
- Fine-tuned on 35B Python tokens.
- Outperforms open Code LLMs.
- Matches or beats OpenAI’s code-cushman-001 (Microsoft Copilot).
- Uses Multi-Query Attention (MQA) for fast inference.
- Includes Fill-in-the-Middle (FIM) capabilities.

---

## StarCoder Safety and Privacy

- Safe release with privacy protections.
- Implements Personal Identifying Information (PII) redaction pipeline.  
- Includes an attribution tool for transparency.
- Released under OpenRAIL-M license.

---

## StarCoder Datasets

- Covers languages like Python, Java, C, Rust.
- Built on **The Stack** dataset.
    - Allows community opt-out from training data.
- Reduces carbon footprint vs. closed models.

---

## StarCoder Evaluation

- Extensive evaluations on coding benchmarks.
    - Superior on HumanEval, MBPP, DS-1000.
    - Better than LLaMA and other previous systems
- Fine-tuning improves Python performance significantly.

---

## REDCODER

- Retrieval-augmented code generation and summarization.  
- Mimics developer behavior by retrieving relevant code/snippets.  
- Retrieves from a code database to assist generation.

---

## SCODE-R

- A dense retrieval model (SCODE-R).
- Improves retrieval over BM25.
- Retrieves both code and summaries.
- Retrieval database includes GitHub, Stack Overflow.

---

## SCODE-G

- Generates code/summaries from retrieved content.
- Based on PLBART transformer model.

---

## RECODER Evaluation

- Evaluated on Java and Python benchmarks.
    - Outperforms prior models on BLEU, CodeBLEU, and Exact Match.
- Retrieval improves code generation accuracy.
- Retrieval improves summarization accuracy.
- Fine-tuned SCODE-R surpasses sparse retrieval methods.
- Human evaluation confirms competitive code quality.

---

## ChatGPT Evaluation

- Yu et al. evaluate ChatGPT for code generation.
- Focus on code generation, completion, and repair.
- ChatGPT acts as both developer and tester.
- Self-verifies generated code using test reports.

---

## Reliability of ChatGPT

- Often misjudges incorrect code as correct.
- Fails to detect vulnerabilities in completed code.
- Incorrectly labels failed repairs as successful.  
- Self-contradicts by later predicting issues in its own code.

---

## ChatGPT Evaluation

- Three self-verification methods used:
  - direct question,
  - guiding question - improves error detection,
  - test report - better identifies vulnerabilities..
- Explanations in test reports often inaccurate.
- Hallucinations lead to inconsistent self-verification.

---

## ChatGPT As Developer

- Findings highlight ChatGPT’s limitations in self-verification.
- Developers must manually verify generated code.
- Self-verification performance varies by programming language.
- Better prompting can improve verification.

---

## CodeBLEU

