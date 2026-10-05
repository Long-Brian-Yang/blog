# 2025-02-09 — Research Presentation: Proton Diffusion & NNP-MD

> **Focus:** five-minute scientific presentation · research structure · transitions

## Presentation Structure

1. **Background / Motivation**
2. **Methodology / Workflow**
3. **Key Results**
4. **Conclusions / Future Work**
5. **Q&A**

## Reading / Model English

Proton-conducting materials are promising for energy-related applications, but accurately simulating proton diffusion with first-principles methods can be computationally expensive.

To address this problem, we use neural-network potentials to accelerate molecular dynamics simulations while aiming to retain near-DFT accuracy.

The workflow combines reference calculations, model training, molecular dynamics simulations at different temperatures, and diffusion analysis.

We calculate the mean squared displacement and estimate diffusion coefficients at different temperatures. The activation energy is then obtained from an Arrhenius analysis.

My work involves developing and evaluating neural-network potentials, running molecular dynamics simulations, analyzing diffusion behavior, writing code, and contributing to research publications.

The next step is to evaluate model transferability and investigate microscopic diffusion mechanisms in greater detail.

## 中文理解

科研发表的核心逻辑是：**为什么做 → 怎么做 → 得到了什么 → 下一步是什么**。五分钟发表尤其需要用 workflow 串联内容，而不是堆积所有技术细节。

## Vocabulary & Chunks

**computationally expensive** — 计算成本高  
**address this problem** — 应对这个问题  
**accelerate molecular dynamics simulations** — 加速 MD  
**retain near-DFT accuracy** — 保持接近 DFT 的精度  
**mean squared displacement** — 均方位移  
**estimate diffusion coefficients** — 估算扩散系数  
**Arrhenius analysis** — Arrhenius 分析  
**activation energy** — 活化能  
**model transferability** — 模型可迁移性  
**microscopic diffusion mechanisms** — 微观扩散机制

## Grammar & Presentation Usage

**To address this problem, ...**

> The calculation is expensive. To address this problem, we use...

**while aiming to...**

> We use NNPs to accelerate MD while aiming to retain near-DFT accuracy.

**The next step is to...** 比反复说 *In the future, I will...* 更自然。

## Natural Spoken English

The basic idea is pretty simple. DFT is accurate, but it's too expensive for long molecular-dynamics simulations. So we train a neural-network potential to reproduce the DFT energy landscape at a much lower computational cost. Then we can run longer simulations and analyze proton diffusion statistically.

## Active Output

1. DFT 很准确，但是长时间 MD 的成本很高。
2. 我们使用 NNP 来加速模拟，同时尽量保持接近 DFT 的精度。
3. 下一步是进一步研究微观扩散机制。

### Suggested Answers

1. DFT is accurate, but long molecular-dynamics simulations are computationally expensive.
2. We use neural-network potentials to accelerate the simulations while aiming to retain near-DFT accuracy.
3. The next step is to investigate the microscopic diffusion mechanisms in greater detail.

## Retelling

Give a one-minute explanation of your research using **problem → method → analysis → next step**.
