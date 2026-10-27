# 29卒：博士研究介绍分层稿

更新：2026-10-27。研究具体结果、个人贡献和发表状态需与最终稿核对。

## 一句话（非专业）
我研究如何用机器学习加速材料中原子运动的模拟，同时检验计算结果是否足够可靠，能用于理解质子在能源材料中的迁移。

## 日语30秒（HR）
「私は計算材料科学を専門とし、機械学習を使って材料内部の原子の動きを調べています。特に、プロトンが材料中をどのように移動するかを、長時間のシミュレーションで解析しています。計算を速くするだけでなく、結果が科学的に信頼できるかを検証することを重視しています。」

## 日语约1分钟（跨专业）
「私の研究テーマは、機械学習原子間ポテンシャルを用いたプロトン拡散の解析です。プロトンが材料内部を移動する仕組みを理解することは、プロトン伝導性材料の研究に関わります。一方、第一原理計算を使った分子動力学では、計算コストの制約から長時間の動きを追うことが難しい場合があります。そこで私は、YをドープしたBaZrO₃を対象に、NEP、MACE、SevenNetという複数の機械学習モデルを比較し、長時間の分子動力学への適用を検討しています。特に、モデルの予測誤差だけでなく、数値的な安定性、拡散の統計的な信頼性、物理的な整合性を含めて評価することが重要だと考えています。」

## English ~1 minute
“My research is in computational materials science, focusing on proton diffusion in yttrium-doped barium zirconate. Understanding proton transport is relevant to proton-conducting materials, but first-principles molecular dynamics can be computationally expensive over long timescales. I study machine-learning interatomic potentials—specifically NEP, MACE, and SevenNet—as a way to investigate longer-time dynamics. An important part of the work is evaluating not only prediction errors but also numerical stability, statistical uncertainty in diffusion, and whether the simulated local structures are physically credible.”

## 5分钟技术讲解结构
1. 问题（40秒）：BZY质子迁移为什么重要；原子尺度与长时间尺度之间的困难。
2. 方法（70秒）：DFT/AIMD参考数据；NEP/MACE/SevenNet比较与fine-tuning（具体流程待核实）。
3. 模拟（60秒）：MD、MSD、扩散系数、温度依赖、RDF；条件和数值暂不写死。
4. 验证（70秒）：能量/力误差≠长时间动力学可信；NVE漂移与波动、统计误差、局部结构。
5. 结论与边界（60秒）：能确定的结果、模型差异、局限；**ACS Omega仍在审稿，不能说已发表**。

## 15分钟专家追问清单
- 为什么选BZY、为什么选Y掺杂与这些浓度？
- DFT设置、AIMD温度/系综/时长、训练数据覆盖和独立测试如何定义？
- 为什么比较NEP、MACE、SevenNet？公平性如何保证？
- Fine-tuning前后指标、训练与验证数据泄漏如何排除？
- Force RMSE是按分量、原子还是构型统计？
- NVE总能量波动与系统性漂移如何区分？单位及归一化是什么？
- 温控器、时间步长、初始构型对扩散有何影响？
- MSD线性区间如何确定？低温采样与多条轨迹不确定性如何处理？
- RDF、Y–H关联、OH再取向、质子跳跃如何联系扩散机制？
- 如何与AIMD/实验对比？哪些结论仍存在限制？
- 自己具体负责了什么？哪些由导师或合作者完成？

## 研究转化为岗位价值
- 基础R&D：提出科学问题、严谨验证、解释微观机制。
- 应用研发：从原子尺度理解材料性能、讨论与实验的连接（不可宣称已做实验）。
- AI/科学计算：训练数据、误差指标与下游模拟可靠性的差别。
- 咨询/技术战略：复杂证据整合、假设检验、沟通技术不确定性。
- 综合职：长期任务、学习新技术、向不同受众解释复杂问题。

## 不能未经确认写入面试的内容
具体数据量、计算时长/超胞大小、扩散系数、模型性能排名、个人独立贡献、已接收/已发表、与实验一致程度。