---
title: "Lint Report 2026-07-07"
date_created: 2026-07-07
date_modified: 2026-07-07
summary: "外部脳vault初期整備後のリンク・構造ヘルスチェック。"
tags: [AIエージェント評価, lint]
type: output
status: final
---

# Lint Report 2026-07-07

## 実施内容

- `AGENTS.md` を追加し、INGEST / QUERY / LINT の運用ルールを定義した。
- `wiki/sources/`, `wiki/concepts/`, `wiki/entities/`, `wiki/syntheses/`, `wiki/outputs/` を作成した。
- `.codex/commands/` に `wiki-ingest`, `wiki-query`, `wiki-lint` の定型プロンプトを追加した。
- 中核概念ページとして [[評価データセット]], [[評価ハーネス]], [[Production Flywheel]], [[LLM-as-a-Judge]], [[Pass@K]] を追加した。

## 残っている主な未解決リンク

以下はIndexに存在するが、まだ個別ページが薄い、または未作成の概念。

- [[AI Evals]]
- [[非決定性]]
- [[評価駆動開発]]
- [[測るレイヤー]]
- [[コードベースグレーダー]]
- [[モデルベースグレーダー]]
- [[人間による評価]]
- [[継続評価]]
- [[アーキテクチャ別の評価設計]]
- [[ツール選択評価]]
- [[エージェントハンドオフ評価]]
- [[RAG評価]]
- [[Vibeベース評価]]
- [[正答率偏重]]

## 推奨次アクション

1. 既存の `wiki/*.md` を `wiki/sources/` と `wiki/concepts/` へ段階的に再配置する。ただしObsidianリンク確認後に行う。
2. `raw/` に新しい記事を追加したら `.codex/commands/wiki-ingest.md` の手順で取り込む。
3. 未解決リンクのうち、複数ソースに登場する概念から優先してページ化する。

