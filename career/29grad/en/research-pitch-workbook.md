# Class of 2029: Research Pitch Workbook

Updated 2026-10-27. Confirm final numerical results, personal contributions and manuscript status before use.

## One-sentence layperson pitch
“I use machine learning to make atomistic simulations of materials more accessible, while testing whether the resulting predictions are scientifically reliable for understanding proton transport.”

## Japanese 30 seconds
「私は計算材料科学を専門とし、機械学習を使って材料内部の原子の動きを調べています。特に、プロトンが材料中をどのように移動するかを、長時間のシミュレーションで解析しています。計算を速くするだけでなく、結果が科学的に信頼できるかを検証することを重視しています。」

## English 1 minute
“My research is in computational materials science, focusing on proton diffusion in yttrium-doped barium zirconate. Understanding proton transport is relevant to proton-conducting materials, but first-principles molecular dynamics can be computationally expensive over long timescales. I study machine-learning interatomic potentials—specifically NEP, MACE, and SevenNet—as a way to investigate longer-time dynamics. An important part of the work is evaluating not only prediction errors but also numerical stability, statistical uncertainty in diffusion, and whether the simulated local structures are physically credible.”

## Japanese ~1 minute
「私の研究テーマは、機械学習原子間ポテンシャルを用いたプロトン拡散の解析です。プロトンが材料内部を移動する仕組みを理解することは、プロトン伝導性材料の研究に関わります。一方、第一原理計算を使った分子動力学では、計算コストの制約から長時間の動きを追うことが難しい場合があります。そこで私は、YをドープしたBaZrO₃を対象に、NEP、MACE、SevenNetという複数の機械学習モデルを比較し、長時間の分子動力学への適用を検討しています。特に、モデルの予測誤差だけでなく、数値的な安定性、拡散の統計的な信頼性、物理的な整合性を含めて評価することが重要だと考えています。」

## Five-minute technical pitch structure
1. Problem (40 sec): Why BZY proton transport matters and why timescales are difficult.
2. Methods (70 sec): DFT/AIMD references and comparison/fine-tuning of NEP, MACE, SevenNet (details to verify).
3. Simulations (60 sec): MD, MSD, diffusion, temperature dependence, RDF.
4. Validation (70 sec): static errors versus long-time dynamics, NVE drift/fluctuations, statistical uncertainty and local structure.
5. Findings and limits (60 sec): verified findings and unresolved issues. **ACS Omega manuscript is under review, not published.**

## Fifteen-minute defense checklist
Why BZY and Y doping? DFT settings; AIMD data coverage; train/test independence; fair comparison of NEP/MACE/SevenNet; fine-tuning gains; force RMSE definition; NVE drift versus fluctuations; thermostat/timestep effects; MSD fitting and low-temperature sampling; RDF/Y–H/OH and hopping mechanisms; AIMD/experimental benchmarks; uncertainty and limitations; individual ownership.

## Role transfer
Fundamental R&D: rigorous science; applied R&D: linking atomistic insight to materials performance; AI/scientific computing: downstream reliability beyond test RMSE; consulting: hypothesis testing and communicating uncertainty; generalist: learning and communicating complex topics.

## Claims requiring verification
Exact training size, supercell/timescale, model ranking, numerical results, individual contribution, publication/acceptance, and agreement with experiments.