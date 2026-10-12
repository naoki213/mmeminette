# 株式会社M.Me.Minette コーポレートサイト

株式会社M.Me.Minette の公式コーポレートサイト（静的サイト）です。
HTML / CSS / JavaScript のみで構成し、ビルド不要で GitHub Pages から配信します。

- 仮公開URL: https://naoki213.github.io/mmeminette/
- 独自ドメイン（予定）: mmeminette.com

## 構成

```
index.html              HOME
philosophy/index.html   PHILOSOPHY（企業理念）※承認待ち原稿
business/index.html     BUSINESS（事業内容）
company/index.html      COMPANY（会社概要）
404.html                404ページ
assets/css/style.css    スタイル
assets/js/main.js       メニュー開閉・スクロール時のフェードイン
assets/img/             ロゴ・アイコン・OGP画像
robots.txt / sitemap.xml / site.webmanifest / favicon.ico
docs/REVIEW.md          正式公開前の確認事項・独自ドメイン移行手順
```

外部依存は Google Fonts（Noto Serif JP / Cormorant Garamond）のみです。

## ローカル確認

```
cd ..
python3 -m http.server 8080
# http://localhost:8080/mmeminette/ を開く
```
