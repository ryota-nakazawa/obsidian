---
title: "Production Flywheel"
date_created: 2026-07-07
date_modified: 2026-07-07
summary: "本番ログと失敗例を評価ケースへ戻し、改善と再評価を継続する循環。"
tags: [AIエージェント評価, evals, concept]
type: concept
status: draft
related: ["[[評価データセット]]", "[[継続評価]]", "[[失敗事例からの評価構築]]"]
source_count: 2
confidence: established
---

# Production Flywheel

## 概要

Production Flywheelは、本番で観測した失敗やユーザー行動を [[評価データセット]] に戻し、改善後に再評価する継続改善ループである。

## ループ

1. 本番ログやユーザーフィードバックを集める
2. 失敗例を評価ケース化する
3. プロンプト、ツール、モデル、ガードレールを改善する
4. 評価ハーネスで再実行する
5. 改善が確認できたら本番へ反映する

## 関連

- [[継続評価]]
- [[失敗事例からの評価構築]]
- [[Observability]]

