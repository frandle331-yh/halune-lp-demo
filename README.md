# HALUNE — Shopify商品販売LP(制作実績用デモ)

架空のスキンケアブランド「HALUNE」を題材にした、Shopify商品販売用ランディングページのデモサイトです。
デザイン支給型のLPコーディング案件を想定し、LP設計〜コーディング〜Shopify組み込み(セクション化)までを一貫して制作しています。

**デモURL**: https://frandle331-yh.github.io/halune-lp-demo/

## 構成セクション

商品紹介ヒーロー / セール価格表示(カウントダウン付き) / 商品説明 / 商品特徴 / アイコン付き説明 / CTA / 関連商品 / フッター

## 技術要素

- HTML / CSS / JavaScript(フレームワーク不使用・単一ファイル)
- レスポンシブ対応(PC 1440px 〜 SP 390px、タブレット確認済み)
- IntersectionObserverによるスクロールフェードイン
- セール締切カウントダウン(JS)
- SP用追従CTAバー
- 画像はすべてSVGで自作(外部画像依存なし・軽量)
- Shopify組み込み用のLiquidセクション一式を `shopify/` に同梱
  (商品ピッカー・compare_at_priceからの割引率自動計算・カートパーマリンク遷移)

## ディレクトリ

```
index.html          … 静的デモLP(GitHub Pages公開用)
shopify/            … Shopifyテーマ組み込み用ファイル(sections / snippets / templates)
portfolio/          … ポートフォリオ掲載用画像
```

※ 掲載している商品・価格・効能・レビュー等はすべて架空です。
