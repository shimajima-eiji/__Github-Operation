---
name: プロジェクト
about: リポジトリ内で関連プロジェクトを管理するために必須
title: "[Project][プロジェクト名]"
labels: 大分類
assignees: ''

---

### プロジェクト
#他Issue(別の大分類) or [ユーザープロジェクト](https://github.com/shimajima-eiji?tab=projects&type=beta より選択)

### Issueテンプレートバージョン
- 2021/12/25(https://github.com/shimajima-eiji/Projects/commit/801d6fd84d66e3493d323c3eda276781a87e4ada)

---

### 備考
以下を設定すること

- プロジェクト

---

### 注記
プロジェクトに設定するカラムを定義する場合は
`[*IssueのOpen/Close][リポジトリ名]*概要`のフォーマットに従う
(リポジトリ名はカラムに加える分には任意とした)
- カラムの概要を特に考慮しない場合は、以下の通り作成するのが望ましい。
  - [Open]調査検討: 起票直後の状態。対応する場合はカラムではなく、アサインする
  - [Close]完了: 対応が完了し、mainにmergeした状態
  - [Close]保留: すぐにやらないが、Issueで見えると
  - [Close]不対応: 対応しないもの。転記した場合もここ
  - [Close]分類Issue: プロジェクトに関連する大分類が複数ある可能性がある
