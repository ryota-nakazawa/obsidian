---
title: "Cost-of-Pass"
date_created: 2026-07-09
date_modified: 2026-07-09
type: concept
domain: research
area: ai
project: ai-evaluation-economics
topic: "LLM評価指標"
summary: "正しい解を1つ得るために期待される金銭コストを表すLLM評価指標。"
tags: [ai, llm, evaluation, cost]
status: draft
---

# Cost-of-Pass

## 概要

Cost-of-Passは、LLMが正しい解を1つ生成するために期待される金銭コストを表す指標である。

モデル `m` が問題 `p` に正解する確率を `Rm(p)`、1回の推論コストを `Cm(p)` とすると、次のように定義される。

```text
v(m, p) = Cm(p) / Rm(p)
```

正答率が高くても推論コストが高ければCost-of-Passは悪化する。逆に、単価が安くても正解確率が低すぎるモデルも悪化する。

## なぜ重要か

- 正答率とコストを1つの経済的指標に統合できる
- [[AI利用量KPI]] やトークン消費量だけでは見えない費用対効果を測れる
- タスクごとに最適なモデルを選びやすくなる
- [[トークンマキシング]] の「使った量」から「成果あたりコスト」へ評価を進められる

## 関連

- [[Frontier Cost-of-Pass]]
- [[推論コスト込み評価]]
- [[人間専門家ベースライン]]
- [[用途開発]]

