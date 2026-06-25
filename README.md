# やまもっちゃんのブログ

テック、日常、グルメ、商品紹介をまとめた個人ブログです。

---

## 📁 ファイル構成

```
yamamoto-blog/
├── index.html        ← トップページ（これだけあれば動く）
├── README.md         ← この説明ファイル
└── articles/         ← 記事ファイルを置くフォルダ（後で作る）
    ├── post-001.html
    └── post-002.html
```

---

## ✍️ 記事を追加する方法

### ステップ1：`index.html` を開いてARTICLES配列に追記

`index.html` の中に以下のようなコメントがある箇所を見つけてください：

```
★ 記事を追加するにはここを編集するだけ！
```

その下の `ARTICLES = [` の配列に、新しい記事オブジェクトを追加します。
**一番上**に追加すると、最新記事が先頭に表示されます。

```js
{
  tag:     "テック",          // カテゴリ（テック/グルメ/日常/商品紹介/自己紹介）
  emoji:   "📱",              // サムネイル絵文字
  thumb:   "thumb-tech",      // 色テーマ（下記参照）
  title:   "記事のタイトル",
  excerpt: "本文の冒頭2〜3文を入れる。",
  date:    "2026年1月1日",
  url:     "articles/post-003.html"  // 記事HTMLのパス
},
```

#### thumb（色テーマ）の選択肢
| 値 | 色 | おすすめカテゴリ |
|---|---|---|
| `thumb-tech`   | 紺 → 青 | テック |
| `thumb-food`   | 黒 → 赤 | グルメ |
| `thumb-life`   | 黒 → 茶 | 日常 |
| `thumb-review` | 黒 → 緑 | 商品紹介 |
| `thumb-about`  | 黒 → 紫 | 自己紹介 |

### ステップ2：記事HTMLを `articles/` フォルダに作る

記事の中身は別ファイル（例：`articles/post-003.html`）を作って書きます。
シンプルなテンプレートを後述しています。

---

## 🚀 GitHub Pages で公開する手順

### 初回セットアップ

1. **GitHubアカウント**がなければ https://github.com で作成

2. **新しいリポジトリを作成**
   - GitHubにログイン → 右上の「+」→「New repository」
   - Repository name: `yamamoto-blog`（好きな名前でOK）
   - Public にチェック
   - 「Create repository」をクリック

3. **ファイルをアップロード**
   - 作成したリポジトリのページで「uploading an existing file」をクリック
   - `index.html` と `README.md` をドラッグ＆ドロップ
   - 「Commit changes」をクリック

4. **GitHub Pages を有効化**
   - リポジトリの「Settings」タブ → 左メニュー「Pages」
   - Source: 「Deploy from a branch」を選択
   - Branch: `main` / `/(root)` を選択 → 「Save」

5. **数分後にURLが発行される**
   ```
   https://あなたのGitHubユーザー名.github.io/yamamoto-blog/
   ```

### 記事を追加・更新するとき

1. ローカルで `index.html` を編集
2. GitHubリポジトリの `index.html` を開き「✏️ Edit this file」
3. 編集内容を貼り付けて「Commit changes」
4. 数秒〜数分でサイトに反映される

---

## 📝 記事ページのシンプルテンプレート

`articles/` フォルダに以下のような `.html` ファイルを作ると記事ページになります：

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>記事タイトル | やまもっちゃんのブログ</title>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400;700&display=swap" rel="stylesheet">
  <style>
    body { font-family: 'Noto Sans JP', sans-serif; max-width: 720px; margin: 0 auto; padding: 40px 20px; color: #111; }
    h1 { font-size: 2rem; line-height: 1.3; margin-bottom: 16px; }
    .meta { color: #888; font-size: 0.8rem; margin-bottom: 40px; }
    p { line-height: 1.9; margin-bottom: 1.5em; }
    a.back { color: #FF6B35; text-decoration: none; font-size: 0.85rem; }
  </style>
</head>
<body>
  <a class="back" href="../index.html">← トップへ戻る</a>
  <h1>記事タイトルをここに書く</h1>
  <div class="meta">2026年1月1日 · テック</div>
  <p>本文をここに書きます。</p>
  <p>段落ごとに &lt;p&gt; タグで囲むだけでOKです。</p>
</body>
</html>
```

---

© やまもっちゃんのブログ
