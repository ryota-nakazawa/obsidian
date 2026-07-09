---
title: "Cost-of-Pass: An Economic Framework for Evaluating Language Models"
date_created: 2026-07-09
date_modified: 2026-07-09
type: source
domain: research
area: ai
project: ai-evaluation-economics
topic: "Cost-of-Pass"
summary: "LLM評価に正答率だけでなく推論コストを組み込み、正解1件あたりの期待コストでモデルを評価する経済的フレームワーク。"
tags: [ai, llm, evaluation, cost, arxiv]
status: draft
source_url: "https://arxiv.org/pdf/2504.13359"
source_pdf: "raw/arxiv-2504.13359-cost-of-pass.pdf"
authors: ["Mehmet Hamza Erol", "Batu El", "Mirac Suzgun", "Mert Yüksekgönül", "James Zou"]
published: "2026-02-26"
---

# Cost-of-Pass: An Economic Framework for Evaluating Language Models

## 取得メモ

- arXiv: 2504.13359
- PDF: https://arxiv.org/pdf/2504.13359
- ローカルPDF: `raw/arxiv-2504.13359-cost-of-pass.pdf`
- 掲載: ICLR 2026 conference paper
- ページ数: 25

## Abstract要約

この論文は、LLMの評価において、性能だけでなく推論コストも同時に扱う必要があると主張する。中心指標は [[Cost-of-Pass]] で、これは「正しい解を1つ得るために期待される金銭コスト」を表す。

さらに、利用可能なモデル群や人間専門家を含めた選択肢の中で、最小のCost-of-Passを [[Frontier Cost-of-Pass]] と定義する。これにより、モデル単体の正答率ではなく、「どのモデルや手法が、どのタスクで、最も経済的に正解を生むか」を比較できる。

## 主要な主張

- LLM導入の経済的価値は、性能が推論コストを上回るかに依存する。
- 正答率だけの評価では、コストの高いモデルや推論時テクニックの実用性を見誤る。
- 軽量モデル、大規模モデル、推論モデルは、それぞれ異なるタスク領域で費用対効果の強みを持つ。
- 複雑な定量問題では、Frontier Cost-of-Passが数カ月単位で半減するような進歩が観測された。
- majority votingやself-refinementのような性能向上手法は、追加コストに見合わないことが多い。
- TALE-EPのような予算意識型の推論手法は、一定の経済的メリットを示す。

## 数式メモ

モデル `m` が問題 `p` に正解する確率を `Rm(p)`、1回の推論試行コストを `Cm(p)` とすると、Cost-of-Passは次で定義される。

```text
v(m, p) = Cm(p) / Rm(p)
```

これは、確率的なモデルが「正解を1つ出すまで」に必要な期待金銭コストを表す。

## 関連しそうな問い

- [[AI利用量KPI]] は利用量ではなく、正解・成果あたりのコストを見るべきではないか。
- [[トークンマキシング]] の次段階として、Cost-of-Passのような費用対効果指標を導入できるか。
- モデル選定では、最高性能モデルではなく、タスクごとの [[Frontier Cost-of-Pass]] を見るべきではないか。
- AI活用の [[用途開発]] では、業務ごとに「正解1件あたりのコスト」を測るべきではないか。

