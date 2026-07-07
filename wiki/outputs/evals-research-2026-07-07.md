---
title: "AI Evals リサーチまとめ 2026-07-07"
date_created: 2026-07-07
date_modified: 2026-07-07
summary: "AI evalsの最新動向を、既存wikiとOpenAI/Anthropicの一次情報をもとに整理したリサーチメモ。"
tags: [AIエージェント評価, evals, research]
type: output
status: final
---

# AI Evals リサーチまとめ 2026-07-07

## 結論

AI evalsは「モデルの点数表」ではなく、AIシステムを継続的に改善するための品質管理ループである。特にAIエージェントでは、単発回答の正誤ではなく、タスク、トライアル、ツール使用、途中経過、最終アウトカムをまとめて測る必要がある。

このvaultでは、既存の [[Master Index - AIエージェント評価]] を中心に、[[グレーダー]]、[[評価データセット]]、[[評価ハーネス]]、[[Production Flywheel]] を中核概念として育てるのがよい。

## 最新動向

- OpenAIのEvalsプラットフォームは、2026-10-31に既存evalが読み取り専用化され、2026-11-30にダッシュボードとAPIが停止予定。したがって、特定のEvals APIではなく、評価設計の原則を残すべき。
- OpenAIはevalsを「Specify -> Measure -> Improve」の業務改善ループとして説明している。企業や個人の文脈では、抽象ベンチマークよりも、実際のワークフローに即したcontextual evalsが重要。
- Anthropicはエージェントevalを、入力を与え、grading logicで成功を測るテストとして整理している。特に自動evalは開発中に実ユーザーなしで回せる点が重要。
- エージェントでは、会話、コーディング、リサーチなど用途ごとに評価形が変わる。ツール選択、状態変化、ターン数、根拠の妥当性、失敗時の回復などが評価対象になる。

## 実務フレーム

1. 目的を定義する

「何ができれば成功か」を、曖昧な満足度ではなく観測可能な条件にする。例: 正しいファイルを作った、根拠付きで回答した、禁止ツールを使わなかった、3ターン以内に解決した。

2. 評価データセットを作る

本番ログ、失敗例、代表ケース、エッジケースを集める。初期は20-50件でもよい。重要なのは、実際に失敗しうる分布に近づけること。

3. グレーダーを設計する

[[コードベースグレーダー]] は高速で再現可能。[[モデルベースグレーダー]] は文章品質や根拠性を扱えるが、判定揺れがある。[[人間による評価]] は高コストだが基準作りと較正に必要。

4. ハーネスで繰り返し実行する

同じタスクを複数回試し、[[Pass@K]] と [[Pass＾K]] を分ける。前者は到達可能性、後者は信頼性を測る。

5. Production Flywheelに戻す

本番で起きた失敗を評価ケース化し、修正後に再実行する。これにより「事故対応」が「再発防止テスト」に変わる。

## このvaultで次に作るべきページ

- [[評価データセット]]
- [[評価ハーネス]]
- [[Production Flywheel]]
- [[LLM-as-a-Judge]]
- [[Pass@K]]
- [[Pass＾K]]
- [[アーキテクチャ別の評価設計]]
- [[エージェントハンドオフ評価]]

## 注意点

- Evals APIや特定UIの手順は寿命が短い。2026年時点ではOpenAIのEvalsプラットフォーム停止予定があるため、設計原則とローカルに残るMarkdown知識を優先する。
- LLM-as-a-Judgeは便利だが、位置バイアス、冗長性バイアス、採点基準の曖昧さに弱い。人間評価との較正が必要。
- 高リスク領域では、1モデルで生成して同じモデルで採点する閉じたループを避ける。別モデルまたは人間レビューを入れる。

## 参照

- [OpenAI API docs: Evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices)
- [OpenAI API docs: Deprecations, 2026-06-03 Evals platform](https://developers.openai.com/api/docs/deprecations#2026-06-03-evals-platform)
- [Anthropic Engineering: Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)
- [[Evaluation Best Practices（OpenAI）]]
- [[AIエージェント評価の極意（note・Anthropic記事解説）]]
- [[AI Evals 評価設計（Arpable）]]
