---
title: "Pass@K"
date_created: 2026-07-07
date_modified: 2026-07-07
summary: "K回の試行のうち1回でも成功する確率を見る、到達可能性の指標。"
tags: [AIエージェント評価, evals, metric]
type: concept
status: draft
related: ["[[Pass＾K]]", "[[評価ハーネス]]"]
source_count: 1
confidence: established
---

# Pass@K

## 概要

Pass@Kは、同じタスクをK回試行したとき、少なくとも1回成功するかを見る指標である。AIが「解ける可能性があるか」を測る到達可能性の指標として使える。

## Pass＾Kとの違い

[[Pass＾K]] がK回すべて成功する安定性・信頼性を重視するのに対し、Pass@Kは探索や候補生成のポテンシャルを重視する。

