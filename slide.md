---
marp: true
theme: gaia
size: 16:9
paginate: true
---
# CSS設計について

～よりよいコーディングライフのために～
<!--
_class: lead
-->

---
## 今回話すこと
1. CSS設計の必要性
2. CSS設計について
3. 設計手法の紹介（3選）
4. まとめ

---
# :one: CSS設計の必要性
<!--
_class: lead
-->

---
## こんな経験ありませんか？
- 同じデザインなのにあっちもこっちも修正しないといけない
- CSSを修正したら意図していないパーツにも影響してしまった
- どこに適用されているのか分からない謎のスタイルがいる
- スタイルが上書きされすぎて`!important`せざるを得ない
- どんなクラス名をつけるべきか悩んでいたら夜が明けた
<!--
> 参考： [スライド](http://takazudo.github.io/presentation-cssarchitecture/#/5)
> 参考： [ウェブ制作者なら意識してほしいCSS設計の基礎知識](https://ics.media/entry/15166/)
-->

---
## ↓↓↓
## CSS設計ですべて解決できます！！
<!--
_class: lead
-->

---
## たとえば、こんな場面
- ある程度のページ数があるWebサイトのHTML/CSSを書くとき
- 複数人で作業するとき
- 長期的にサイトの管理をするとき

---
# :two: CSS設計について
<!--
_class: lead
-->

---
## なんのために？
- メンテナンス性の向上
- 作業の効率化

## なにをするの？
- HTMLクラス名の規則を考える
- CSSのコードの管理方法を考える

---
## よいCSSとは

1. 予測できる
2. 再利用できる
3. 保守できる
4. 拡張できる

> 参考：[GoogleのエンジニアPhilipWalton氏のブログ](https://philipwalton.com/articles/css-architecture/)

---
## 1.予測できる

- クラス名を見れば何に使われているかすぐにわかる
- クラス名がユニークになることにより、想定外の不具合が起きない
- 特定の要素を探す時に役立つ

---
:x: NG例：どこで使ってるスタイル？？
```css
.bt { ... }
.red { ... }
.box04 .top { ... }
```

:o: OK例：あれのスタイルかな？
```css
.button { ... }
.is-error { ... }
.index-greeting .title { ... }
```

---
## 2.再利用できる

- コードを書き直したり上書きする手間がない状態
- スタイリングが抽象化されている
- スタイリングが適切に分離されている

---
:x: NG例：同じスタイルがたくさん…
```css
.news .link { ... }
.gallery .link { ... }
.box01 .button { ... }
```

:o: OK例：共通のボタンとして使いまわせる
```css
.common-button { ... }
```

---
## 3.保守できる

- こんなときに既存のCSSをリファクタリングする必要がない
  - 新しいコンテンツや機能を追加した
  - コンテンツの位置を変更した　など

---
:x: NG例：既存のスタイルがジャマだな…
```css
.contents ul { ... }
.contents .index-add ul { ... }
```

:o: OK例：新しくulのスタイルが書けるな
```css
.index-old ul { ... }
.index-add ul { ... }
```

---
## 4.拡張できる

- 携わる人が複数人になっても、問題なく管理できる状態
- CSS設計の規則はわかりやすく、学習コストが極端に高くないものがよい

---
## で？具体的にどうすればいいの！？
<!--
_class: lead
-->

---
## ↓↓↓
## 既存の設計手法を活用しよう！
<!--
_class: lead
-->

---
# :three: 設計手法の紹介（3選）
<!--
_class: lead
-->

---
## 有名な3つの設計手法
- BEM（MindBEMding）
  - [Get BEM](http://getbem.com/)
  - [BEM公式ページ_日本語訳](https://qiita.com/yuta_web/items/6f2aa6b69e70b0b9f86c)
  - [BEM(MindBEMding)によるCSS設計](https://github.com/manabuyasuda/styleguide/blob/master/how-to-bem.md)
- OOCSS
  - [Object-Oriented CSS](http://oocss.org/)
- SMACSS
  - [Scalable and Modular Architecture for CSS](http://smacss.com/ja)

---
## BEM（MindBEMding）とは
- Block/Element/Modifier で構成
  - Block … 構成のルートとなる要素
  - Element … Blockの子要素
  - Modifier … BlockやElementの装飾や動作のパターン
- MindBEMding … BEMをCSSのクラス名に適用するために作られた規則のこと

---
## BEMで書いた例
- 

---
## OOCSSとは
- Object-Oriented CSS … オブジェクト指向CSS
- 構造と見た目を分離する
- コンテナとコンテンツを分離する

---
## OOCSSで書いた例

---
## SMACSSとは
- Scalable and Modular Architecture for CSS
  （日本語訳：拡張可能かつモジュール的なCSS設計）
- CSSを5つのカテゴリに分類して管理
  - Base … 要素そのもののデフォルトスタイル
  - Layout … ページをエリアごとに分割
  - Module … 再利用可能なパーツ
  - State … レイアウトやモジュールの特定の状態を示す
  - Theme … サイトのルック＆フィールを定義
---
## SMACSSで書いた例

---
## 他にも…
- PRECSS
- MCSS
- FLOCSS 　などがあるよ

---
# :four: まとめ
<!--
_class: lead
-->

---
## 書き比べてみた感想

---
## 設計はよいもの！

- 設計手法を理解して利用することで、結果的に作業の効率化につながる！
- UIの部品化などのコンポーネント思考は、CSS以外でも有用な考え方

---
# :five: おまけ
<!--
_class: lead
-->

---
## 参考文献
- [CSS設計完全ガイド　～詳細解説＋実践的モジュール集](https://www.amazon.co.jp/dp/429711173X/ref=cm_sw_em_r_mt_dp_Z35SG2QWFQG0S0W1WRK2)
![bg fit right:38%](./img/2022-01-13-18-21-40.png)

---
## その他、参考にした記事のリンク集
- [脱CSS無法地帯！！CSS設計を取り入れてWebサイトのメンテナンス性を向上！](https://www.gpol.co.jp/blog/101)
- [CSS設計って勉強しなきゃいけないの？~CSS設計完全ガイドを読んで~](https://fixel.co.jp/blog/css-design-1/)
- [【CSS設計手法】BEM、OOCSS、SMACSSの違いと特徴のまとめ](https://webdesign-trends.net/entry/9214)
- [CSS設計とは？設計手法はどれがいいのかまとめてみた](https://depart-inc.com/blog/css-design/)
- [CSS設計の基本](https://qiita.com/tera_shin/items/af90aeba49f93c76bd9e)

---
## 今回のスライドについて

VSCodeの拡張機能+Markdownで書きました！
マウス操作なしでサクサク便利:smile::pray::sparkles:
- 拡張機能
  - [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)
- 参考記事
  - [【VS Code + Marp】Markdownから爆速・自由自在なデザインで、プレゼンスライドを作る](https://qiita.com/tomo_makes/items/aafae4021986553ae1d8)

---
# ご清聴ありがとうございました:bow:
よいコーディングライフを！
<!--
_class: lead
-->
