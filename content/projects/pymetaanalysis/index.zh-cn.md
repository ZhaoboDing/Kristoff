---
title: "PyMetaAnalysis"
date: 2026-07-22
description: "一个贴近 pandas 使用习惯、让分析过程有迹可循的 Python Meta 分析库。"
summary: "一个贴近 pandas 使用习惯的 Python Meta 分析库，尽量把计算过程和每一步选择都交代清楚。"
tags: ["Python", "统计学", "开源"]
showBreadcrumbs: true
showTableOfContents: true
showRelatedContent: false
showPagination: false
---

**PyMetaAnalysis** 是一个用 Python 汇总多项研究结果的开源 Meta 分析库。做这个项目时，我一直在想一件事：统计工具可以好用，但不能只给出一个答案，却不告诉使用者这个答案是怎么来的。

<div class="flex flex-wrap gap-3 my-6">
{{< button href="https://github.com/ZhaoboDing/PyMetaAnalysis" target="_blank" >}}
在 GitHub 查看源码
{{< /button >}}
{{< button href="https://zhaoboding.github.io/PyMetaAnalysis/" target="_blank" >}}
阅读完整文档
{{< /button >}}
</div>

## 为什么做这个项目

实际做 Meta 分析时，数据通常已经整理在 pandas DataFrame 里。可不少工具仍要求先把数据改成它所期待的格式，整个分析过程也常常散落在不同函数和临时变量之间。

我想做一个更符合 Python 日常使用习惯的工具：数据可以直接传入，结果也不只是一组数字。哪些研究被纳入、哪些被排除、用了什么权重和方法、遇到特殊数据时怎么处理，都应该能从结果里查到。

因此，PyMetaAnalysis 可以直接接收 DataFrame、NumPy 数组或普通 Python 序列，并把单项研究效应、排除原因、权重、诊断信息、方法选择和计算记录统一收在一个不可变的结果对象里。

## 支持的分析

- 通用效应量：输入抽样方差或标准误即可
- 二分类结局：支持优势比、风险比和风险差
- 连续型结局：支持均数差和 Hedges' *g*
- 固定效应、随机效应和 Mantel–Haenszel 模型
- REML、Paule–Mandel 和 DerSimonian–Laird 异质性估计方法
- 亚组分析、逐一剔除分析和累积 Meta 分析
- 可选的 Matplotlib 绘图支持，包括森林图和漏斗图
- 可以导出 JSON 或 Markdown 报告，方便保存和进一步处理

## 让每一步都有迹可循

如果某一行因为缺失值或稀疏数据规则而没有进入计算，它不会悄悄消失：结果中仍会保留它的编号和具体排除原因。像“把标准误换算成方差”这样的处理也会被记录下来。对于比值类指标，程序会同时保留用于模型计算的原始尺度和更直观的展示结果。

为了确认计算结果靠谱，我用手工计算、统计性质检查和各种边界案例做测试，也把部分结果与 R 的 `metafor` 包交叉核对。持续集成目前覆盖 Python 3.10–3.13，同时检查类型、代码规范、文档和发行包。

## 一个简单示例

```python
import meta_analyze as ma

result = ma.meta_analysis(
    effect=[0.12, 0.35, -0.08, 0.21],
    variance=[0.04, 0.06, 0.03, 0.05],
    study=["Trial A", "Trial B", "Trial C", "Trial D"],
    model="random",
    tau2_method="REML",
)

print(result.summary())
print(result.study_results)
```

在 PyPI 上安装时使用 `PyMetaAnalysis`，代码里的导入名则是 `meta_analyze`。项目采用 MIT 许可证，目前还在 0.x 的早期阶段，接口仍有可能调整。
