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

- New evaluation metric for code synthesis.  
- Improves BLEU by considering code syntax and semantics.  

$$
\mathrm{CodeBLEU} = \alpha \cdot \mathrm{BLEU} + \beta \cdot \mathrm{BLEU}_\mathrm{weight}\\ + \gamma \cdot \mathrm{AST} + \delta \cdot \mathrm{DataFlow}
$$

---

## BLEU

- Most important metric for machine translation evaluation

$$
\mathrm{BLEU} = \mathrm{BP} \cdot \exp\left(\sum_{n=1}^N w_n \log p_n\right)
$$

- BLEU score is the geometric mean of n-gram precisions.
- Typically $w_1 = \ldots = w_N = \frac{1}{N}$.

---

## BLEU

- **Precision** is the ratio of n-grams in the candidate to the reference.

$$
p_n = \frac{\sum_{C \in \mathrm{Candidates}}\sum_{i=1}^n c^C_\mathrm{clip}(i\ldots i+n)}{\sum_{C \in \mathrm{Candidates}}\sum_{i=1}^n c^C(i\ldots i+n)}
$$

- $c_\mathrm{clip}^C$ is the count of n-grams in the candidate that appear in the reference.

---

## CodeBLEU - Weighted BLEU

- Uses weighted n-gram match for keywords.

$$
p_n = \frac{\sum_{C \in \mathrm{Candidates}}\sum_{i=1}^n \mu_n^i c_\mathrm{clip}^C(i\ldots i+n)}{\sum_{C \in \mathrm{Candidates}}\sum_{i=1}^n \mu_n^i c^C(i\ldots i+n)}
$$

- $\mu_n^i = 5$ for keywords, $1$ otherwise.

---

## CodeBLEU - AST Match

- Leverages abstract syntax trees (ASTs) for structure.

$$
\mathrm{AST} = \frac{c_\mathrm{clip}(T_\mathrm{cand})}{c(T_\mathrm{ref})}
$$

---

## CodeBLEU - Data-Flow Match

- Incorporates data-flow analysis for semantics.
- Difference between `return x` and `return y` is captured.
- Ensures logic correctness is evaluated.

---

## CodeBLEU Evaluation

- Better correlation with human evaluation scores.
- Evaluated on text-to-code, translation, and refinement tasks.
- Surpasses BLEU and perfect accuracy in reliability.
- Hyperparameter tuning improves correlation.

---

## Summary

- Code generation systems like StarCoder, REDCODER, and ChatGPT are evaluated.
- Techniques from large language modelling are applied to code generation.
- CodeBLEU is a new metric for code synthesis evaluation.

