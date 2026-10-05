# 2025-02-18 — Research Proposal English: Y-Doped BaZrO₃ & Neural-Network Potentials

> **Focus:** research proposal · NNP fine-tuning · active learning · AIMD/MD · diffusion analysis

## 1. Research Objective

The objective is to develop and validate neural-network potentials for studying proton diffusion in Y-doped BaZrO₃.

The project compares pretrained machine-learning potentials such as M3GNet and CHGNet, explores fine-tuning strategies using system-specific first-principles data, and evaluates whether the resulting models can reproduce diffusion behavior with sufficient accuracy.

## 2. Proposed Workflow

### Step 1 — Reference Data

Generate representative structures and reference energies and forces using first-principles calculations.

The dataset should cover relevant local environments, temperatures, proton configurations, and structural distortions.

### Step 2 — Fine-Tuning

Fine-tune pretrained models using BaZrO₃-specific data rather than training entirely from scratch.

The goal is to determine whether transfer learning can reduce the amount of expensive first-principles data required while maintaining accuracy for the target system.

### Step 3 — Active Learning

Use an iterative active-learning workflow to identify structures where the model is uncertain or likely to extrapolate.

These structures can then be recalculated using first-principles methods and added to the training set.

### Step 4 — AIMD Validation

Compare machine-learning-potential trajectories with short ab initio molecular dynamics simulations at selected temperatures.

The comparison should examine structural distributions, energies, forces, and proton dynamics.

### Step 5 — Long MD Simulations

After validation, use the machine-learning potential to run longer molecular-dynamics simulations over a wider temperature range.

### Step 6 — Diffusion Analysis

Calculate the proton mean squared displacement and obtain the diffusion coefficient, D, from the long-time slope.

Then use an Arrhenius relationship to estimate the activation energy, Ea.

## 3. 中文理解

整体 workflow 是：

**DFT reference data → pretrained model fine-tuning → active learning → AIMD validation → long-time MLIP-MD → MSD / D → Arrhenius Ea**

研究问题不是单纯“哪个模型更准”，还包括：预训练模型能否通过 system-specific 数据高效迁移到 Y-doped BaZrO₃，以及模型是否能够可靠描述真正关心的质子扩散动力学。

## 4. Key Vocabulary & Chunks

| Expression | 中文 |
|---|---|
| **develop and validate** | 开发并验证 |
| **system-specific data** | 针对特定体系的数据 |
| **fine-tune a pretrained model** | 微调预训练模型 |
| **train from scratch** | 从头训练 |
| **reduce the amount of... required** | 减少所需……数量 |
| **active-learning workflow** | 主动学习流程 |
| **identify uncertain structures** | 识别不确定结构 |
| **extrapolate** | 外推 |
| **add to the training set** | 加入训练集 |
| **ab initio molecular dynamics** | 第一性原理分子动力学 |
| **wider temperature range** | 更宽温度范围 |
| **long-time slope** | 长时间区域斜率 |
| **Arrhenius relationship** | Arrhenius 关系 |
| **estimate the activation energy** | 估算活化能 |

## 5. Grammar & Research Usage

### rather than + -ing

> Fine-tune pretrained models **rather than training entirely from scratch**.

### determine whether...

> The goal is to determine **whether transfer learning can reduce** the required reference data.

### After + noun / -ing

> **After validation**, use the model for longer simulations.

### structures where...

> Identify structures **where the model is uncertain**.

## 6. Natural Spoken English

The basic plan is to start from pretrained machine-learning potentials and adapt them to Y-doped BaZrO₃ using a relatively small amount of system-specific DFT data.

Instead of just training once and hoping the model works, I want to use an active-learning loop. If the model encounters structures where it's uncertain, we can send those structures back to DFT, add them to the dataset, and retrain.

Once the model is validated against short AIMD simulations, we can use it for much longer MD runs and calculate proton diffusion coefficients and activation energies.

## 7. Expression Upgrade

**Basic**

> We use more data when the model is bad.

**Better**

> We use active learning to identify uncertain configurations and selectively expand the training set.

**Basic**

> Then we calculate diffusion.

**Better**

> After validating the potential, we use long-timescale MD to extract diffusion coefficients and estimate the activation energy from Arrhenius behavior.

## 8. Active Output Practice

1. 我们希望使用针对该体系的 DFT 数据微调预训练模型。
2. 主动学习可以帮助识别模型不确定的结构。
3. 这些结构可以重新进行第一性原理计算并加入训练集。
4. 在短 AIMD 验证后，可以运行更长时间的 MD。
5. 最终从 MSD 得到扩散系数，并通过 Arrhenius 分析估算活化能。

### Suggested Answers

1. We aim to fine-tune pretrained models using system-specific DFT data.
2. Active learning can help identify structures where the model is uncertain.
3. These structures can be recalculated with first-principles methods and added to the training set.
4. After validation against short AIMD simulations, we can run much longer MD simulations.
5. Finally, we obtain diffusion coefficients from the MSD and estimate the activation energy using an Arrhenius analysis.

## 9. Retelling Challenge

Explain the complete workflow in 2 minutes without looking:

**reference data → fine-tuning → active learning → AIMD validation → long MD → D / Ea**

## 10. My Notes

- Workflow transitions:
- Technical terms I want to pronounce better:
- Questions about validation:
- My short proposal version:
