# Shopify 組み込み用ファイル

`index.html`(静的デモ)を Shopify テーマ(Online Store 2.0)へ移植するためのサンプル実装です。
カスタマイザーから商品・文言・バッジ・特典表示をノーコードで編集できる設計にしています。

## 構成

```
shopify/
├─ sections/
│  ├─ lp-hero.liquid      … 商品紹介ヒーロー(商品ピッカー・バッジblock対応)
│  ├─ lp-price.liquid     … セール価格表示(compare_at_priceから割引率を自動計算、カウントダウン付き)
│  └─ lp-related.liquid   … 関連商品(コレクション指定 / 個別指定の両対応)
├─ snippets/
│  └─ lp-product-card.liquid
└─ templates/
   └─ page.lp.json        … LP用ページテンプレート
```

## 導入手順

1. 管理画面 → オンラインストア → テーマ → コードを編集
2. `sections/` `snippets/` `templates/` に上記ファイルを追加
3. `assets/lp-styles.css` を追加(index.html の `<style>` 内容をクラス名 `lp-` プレフィックスで移植)
4. ページを新規作成し、テーマテンプレートに `page.lp` を選択
5. カスタマイザーで販売商品・文言・セール締切日時を設定

## 実装ポイント

- 購入導線は `{% form 'product' %}`(POST /cart/add)。ヒーローのCTAは
  `{{ routes.cart_add_url }}?id={{ variant.id }}` のカートパーマリンクでカート直行。
- セール表示は商品側の「割引前価格(compare_at_price)」を参照し、割引率をLiquidで自動計算。
  価格変更時にLPの修正が不要になります。
- 画像は `image_url` + `image_tag` フィルタで srcset/sizes を自動生成し、表示速度を確保。
- スキーマの `presets` を定義済みのため、セクションは「セクションを追加」から自由に再利用できます。
