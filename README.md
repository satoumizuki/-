# 卒業制作カウントダウン

卒業日から逆算して、卒業制作の各STEP（README → 画面遷移図 → ER図 → issue → MVP）の
「着手目安日」を自動で計算し、そのタイミングでそっと背中を押す学習トラッカーです。

- 週の学習時間を入れると、目安日がペースに合わせて自動で前後します
- 各STEPにはレビュー・修正ぶんの余裕（見積り＋25%）を織り込み済み
- 設計フェーズは、目安を過ぎても未着手だと声かけのトーンが段階的に上がります
  （🔥 そろそろ → 👀 もう着手できてる? → 🤝 一緒に進めよう）
- 進捗はブラウザの localStorage に保存されます

## 公開に必要なファイル（GitHub Pages）

リポジトリのルートに、以下をそのまま置いてください。

```
index.html              ← アプリ本体
manifest.webmanifest    ← ホーム画面追加用
icon-192.png / icon-512.png
apple-touch-icon.png
favicon-64.png
og.png                  ← SNS共有カードの画像
README.md
```

`verify.html` は動作確認用のツールです。**受講生に配る公開URLには置かないでください**
（自分でテストするときだけローカルや別ブランチで使うのがおすすめ）。

## デプロイ手順

1. GitHub でリポジトリを作成し、上記ファイルをアップロード（またはコミット）
2. Settings → Pages → Build and deployment → Source を「Deploy from a branch」
3. Branch を `main` / `(root)` にして Save
4. 数分後、`https://<ユーザー名>.github.io/<リポジトリ名>/` で公開されます

## 公開後にやると良いこと

- OGカードのプレビューが最新にならないときは、Slack なら URL を貼り直す、
  X なら [Card Validator](https://cards-dev.twitter.com/validator) でキャッシュ更新
- より確実にするなら、`index.html` の `og:image` を相対パス `og.png` から
  絶対URL `https://<ユーザー名>.github.io/<リポジトリ名>/og.png` に変えてください

## 注意

- 進捗データは **ブラウザ・端末ごとに別** です（スマホとPCで同期しません）。
  受講生には「各自の端末に保存される」前提を伝えると親切です。
- バックエンドはありません。個人情報も送信しません。
