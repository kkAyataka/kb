# コードビューのベストプラクティス

**更新:** 2026-06-14  
**分類:** コードレビュー  

## コードレビューのレビューサイズに関する研究・知見

コードレビューでは、**一度にレビューする変更量を小さく保つこと**が重要とされている。レビュー対象が大きくなるほど、レビューアーの集中力が落ち、欠陥や設計上の問題を見落としやすくなるためである。

SmartBear は、ピアコードレビューの実務上の目安として、**1回のレビューは 200〜400 LOC 程度**に抑えることを推奨している。また、レビュー速度は **500 LOC/時 未満**、レビュー時間は **60分以内**が望ましいとしている。これは、レビュー対象が大きすぎたり、レビュー速度が速すぎたりすると、欠陥検出率が低下するためである。

出典: SmartBear, *Best Practices for Peer Code Review*
<https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/>

Microsoft の研究でも、レビュー対象が大きくなるとレビューコメントの有用性が下がる傾向が報告されている。Bosu らは Microsoft の複数プロジェクトにおけるコードレビューコメントを分析し、**変更ファイル数が多いレビューほど、作者にとって有用なコメントの割合が低下する**ことを示している。

出典: Bosu, Greiler, Bird, *Characteristics of Useful Code Reviews: An Empirical Study at Microsoft*
<https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/bosu2015useful.pdf>

McIntosh らの研究では、現代的コードレビューにおいて、単にレビューが行われたかどうかだけでなく、**レビューカバレッジ、レビューへの参加度、対象領域に詳しいレビュアーの関与**がソフトウェア品質と関係することが示されている。また、速すぎるレビューは低品質なコードを通しやすいリスクがあるとされている。

出典: McIntosh et al., *An Empirical Study of the Impact of Modern Code Review Practices on Software Quality*
<https://rebels.cs.uwaterloo.ca/papers/emse2016_mcintosh.pdf>

以上を踏まえると、レビューサイズの実務上の目安は次のように整理できる。

- **400 LOC を超える場合は分割を検討する**
- **変更ファイル数が多い場合は分割を検討する**
- **1時間以上かかるレビューは、観点別レビューや分割レビューにする**
- **速すぎる LGTM を避ける**
- **大きな変更では、対象領域に詳しいレビュアーを含める**

ただし、`400 LOC` という数値は絶対的な基準ではなく、あくまで目安である。重要なのは、**レビューアーが変更内容を理解し、意味のある指摘ができるサイズに保つこと**である。
