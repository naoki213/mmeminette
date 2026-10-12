# 正式公開前の確認事項

## 1. 承認待ち原稿（企業理念）

以下は制作側による**提案文**であり、会社として正式に決定した理念ではありません。
HTML内では `<!-- DRAFT（承認待ち原稿） -->` コメントで範囲を示しています。

| 掲載箇所 | 内容 |
| --- | --- |
| `philosophy/index.html` | 企業理念「商品と人をつなぎ、日々の暮らしに新しい価値を。」／本文3段落／大切にする姿勢（誠実さ・価値の提供・挑戦） |
| `index.html`（Philosophyセクション） | 上記理念の要約 |

承認後は DRAFT コメントを削除してください。修正がある場合は該当箇所の文言を差し替えてください。

## 2. 制作側で作成・調整した文言（要確認）

- HOME メインコピー「暮らしに寄り添う価値を、届ける。」・サブコピー（指示書案をほぼそのまま使用）
- HOME About見出し「人と商品を、丁寧につなぐ会社です。」と紹介文
- BUSINESS 各事業の説明文・「事業の概要」「想定している領域」の箇条書き
- BUSINESS ECショップの状況表示「準備中」と注記
- BUSINESS TikTok Shop に関する注記（外部プラットフォームである旨・商標表記）
- 英字見出し（About / Business / Philosophy / Company / Integrity / Value / Challenge 等）

## 3. ロゴの使用方法

- ヘッダーでは、ロゴを「エンブレム（猫とリース）」と「社名ロゴタイプ（株式会社 M.Me.Minette）」に分割し横並びで使用しています（縦横比は維持）。この組み方でよいかご確認ください。
- 提供ロゴの背景に残っていた半透明のノイズを除去して使用しています。
- 正式なロゴデータ（AI / SVG / 高解像度PNG）があれば差し替えを推奨します。

## 4. 写真素材

- `business/` EC・商品販売事業の写真（`assets/img/business-ec-*`）はご提供いただいた画像です。「※写真はイメージです。実際の取扱商品とは異なります。」と注記しています。
- 画像の利用権（生成AI画像の場合は利用規約上の商用利用可否を含む）をご確認ください。

## 5. 情報の確認

- 会社名・所在地・設立日・メールアドレスが登記内容等と一致しているか
- 事業内容の表記が定款の目的と齟齬がないか
- Googleマップのリンク先（検索結果）が正しい建物を示しているか
- support@mmeminette.com が受信可能であること

## 6. 独自ドメイン（mmeminette.com）移行時の作業

**メール（MX / SPF / DKIM / DMARC）に関わるDNSレコードは変更・削除しないこと。**

1. GitHub リポジトリ Settings → Pages → Custom domain に `mmeminette.com`（または `www.mmeminette.com`）を設定（リポジトリ直下に `CNAME` ファイルが作成されます）
2. DNS に Web 用レコードのみ**追加**する
   - apex（mmeminette.com）: A レコード 185.199.108.153 / 185.199.109.153 / 185.199.110.153 / 185.199.111.153（必要に応じ AAAA 2606:50c0:8000::153 〜 8003::153）
   - www: CNAME `naoki213.github.io`
   - 既存の apex に A レコードやメール用レコードがある場合は、内容を確認してから作業する（MXレコードはそのまま残す）
3. GitHub の Settings → Pages で DNS チェック完了後、「Enforce HTTPS」を有効化
4. （推奨）GitHub アカウント設定 → Pages で `mmeminette.com` をドメイン認証（乗っ取り防止）
5. サイト内の絶対URLを置換: `https://naoki213.github.io/mmeminette/` → `https://mmeminette.com/`
   - 対象: 各HTMLの canonical / og:url / og:image / 構造化データ、`sitemap.xml`、`robots.txt`
   - `404.html` 内の `/mmeminette/` パスを `/` に変更
6. Google Search Console にドメインを登録し sitemap.xml を送信
