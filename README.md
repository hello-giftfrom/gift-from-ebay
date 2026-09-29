# GIFT FROM 公式Webサイト

HTML / CSS / JavaScriptのみ。ビルド・外部ライブラリ・外部フォント通信は不要です。画像も同梱しています。

## 公開前に変更する箇所

`index.html` で `CHANGE_ME` を検索してください。

| 未設定文字列 | 箇所 | 変更内容 |
|---|---|---|
| `CHANGE_ME_EMAIL` | COMPANYの連絡先、CONTACT（計2箇所） | 実際に受信できる事業用メールアドレス |
| `CHANGE_ME_SITE_URL` | head内の `og:url`（1箇所） | GitHub Pagesの公開URL。例：`https://YOUR_USERNAME.github.io/gift-from/` |

会社名・所在地・事業内容が登録時の情報と一致するか確認してください。代表者・詳細住所・法人番号などは未提供のため追加していません。掲載写真はイメージ素材で、実際の商品・事業所・従業員の証明ではありません。本サイトの公開は各サービスの審査通過を保証するものではありません。

## 1. GitHubへpush

GitHubで空のリポジトリ（例：`gift-from`）を作成し、このREADMEがあるフォルダで実行します。GitHub側でREADMEなどを自動追加しないでください。

```sh
git init -b main
git add .
git commit -m "Create GIFT FROM corporate website"
git remote add origin https://github.com/YOUR_USERNAME/gift-from.git
git push -u origin main
```

`YOUR_USERNAME` とリポジトリ名は実際のものに置換してください。GitHubへのログイン・認証が必要です。GitHub Freeの場合は公開リポジトリを使用してください。

## 2. GitHub Pages公開

1. リポジトリの **Settings → Pages** を開きます。
2. **Build and deployment → Source** で **Deploy from a branch** を選択します。
3. Branchを **main**、フォルダを **/ (root)** にして **Save**。
4. 数分後、Pages画面の公開URLを開きます。
5. `index.html` の `CHANGE_ME_SITE_URL` をそのURLに置換し、再pushします。

```sh
git add .
git commit -m "Update company contact and site URL"
git push
```

相対パスを使っているため、プロジェクト配下のPages URLでも動作します。公開後、画像表示・メニュー・メールアドレスを確認してください。

## 3. 画像差し替え場所

すべて `assets/images/` にあります。同じファイル名で置換するだけです。

| ファイル | 用途 | 推奨比率 |
|---|---|---|
| hero.jpg | 富士山などのメイン写真 | 16:9、幅1920px程度 |
| toys.jpg | 知育玩具・ホビー | 4:3 |
| electronics.jpg | カメラ・家電 | 4:3 |
| japanese-goods.jpg | 日本の暮らしの道具 | 4:3 |
| culture.jpg | アニメ・カルチャー | 4:3 |
| packing.jpg | 梱包・発送 | 正方形前後 |
| favicon.svg | GFの文字アイコン | 正方形 |

画像内容を変える場合は、`index.html` の該当 `img` の `alt` も更新してください。写真の出典は `assets/images/CREDITS.md` に記載しています。

## 4. メールアドレス変更場所

`index.html` 内の `CHANGE_ME_EMAIL` を2箇所とも置換します。表示のみの仕様です。クリックでメールを開く場合は `<a href="mailto:実際のメールアドレス">実際のメールアドレス</a>` にできます。

## 5. 会社情報変更場所

`index.html` の `<dl class="company-list">` 内にあります。テキストロゴとフッターも同じファイル内です。色・余白・レスポンシブの設定は `styles.css`、スマホメニューは `script.js` にあります。

## ローカル確認

`index.html` をブラウザで直接開くか、このフォルダで以下を実行します。

```sh
python3 -m http.server 8000
```

`http://localhost:8000` を開いてください。サーバー停止は `Ctrl+C`。
