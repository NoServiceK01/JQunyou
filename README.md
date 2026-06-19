# JR九州 運用サイト

GitHub Pages で公開できる静的サイトです。

- `index.html`: 閲覧用ページ
- `admin.html`: 管理用ページ
- 初期ID: `No_Service_unyou`
- 初期パスワード: `1c6e3ea006539`

管理画面では、路線ごとに運用番号、所定、列車番号を登録できます。閲覧画面では路線を選択し、どれどれの HTML から列車番号、行先、列車種別、運行状況を読み取って表示します。

GitHub Pages は静的ホスティングのため、JR九州側の CORS 設定によっては `https://george-doredore.jrkyushu.co.jp/ip/...` を直接取得できません。その場合は管理画面の「CORSプロキシURL」に、取得対象 URL を末尾に付けて返すプロキシを設定してください。

## ローカル確認

```bash
node dev-server.js
```

起動後、`http://127.0.0.1:4173/` を開きます。

## 注意

この版は GitHub Pages だけで動く静的サイトなので、登録した運用やログイン情報はブラウザの `localStorage` に保存されます。複数端末・複数ユーザーで同じデータを共有する本番運用には、Firebase、Supabase、GitHub Actions 経由の JSON 更新など、別途バックエンドが必要です。

また、静的サイト上のログインは画面上の簡易ロックです。公開 GitHub Pages で管理画面を完全に秘匿する用途には向きません。
