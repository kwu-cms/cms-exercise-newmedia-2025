# メディア表現発展演習Ⅰ - 課題提出データ表示ページ

GitHub Pagesで公開する静的Webアプリケーションです。学生の課題作品をギャラリー形式で表示します。

## 機能

- 課題作品のギャラリー表示（Masonryレイアウト）
- マルチタグ検索機能（分類別カラーリング）
- 無限スクロール対応
- 画像のLazy Loading
- 詳細ビュー（作品の詳細情報とレポート表示）
- レスポンシブデザイン対応
- コンパクトヘッダー（スクロール時に自動切り替え）

## 技術スタック

- **フロントエンド**: HTML5, CSS3, JavaScript (ES6+)
- **ホスティング**: GitHub Pages
- **データ形式**: JSON（静的ファイル）

## プロジェクト構造

```text
プロジェクトルート/
├── public/
│   ├── index.html          # メインページ
│   ├── css/
│   │   └── style.css      # スタイルシート
│   ├── js/
│   │   └── app.js         # フロントエンドJavaScript
│   ├── data/
│   │   └── assignments.json  # 課題データ（JSON）
│   └── images/            # 課題画像
├── .gitignore
├── package.json
└── README.md
```

## GitHub Pagesでの公開

### セットアップ手順

1. **リポジトリをGitHubにプッシュ**

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
   git branch -M main
   git push -u origin main
   ```

2. **GitHub Pagesの有効化**
   - GitHubリポジトリの「Settings」→「Pages」に移動
   - 「Source」で「Deploy from a branch」を選択
   - 「Branch」で「main」を選択
   - 「Folder」で「/ (root)」を選択
   - 「Save」をクリック

3. **サイトの確認**

   数分後、以下のURLでサイトにアクセスできます：

   ```text
   https://YOUR_USERNAME.github.io/YOUR_REPOSITORY_NAME/
   ```

### データの更新

`public/data/assignments.json`ファイルを編集してコミット・プッシュすると、自動的にサイトが更新されます。

画像ファイルは`public/images/`フォルダに配置してください。

## ローカル開発

### 静的ファイルサーバーで確認

```bash
# publicフォルダに移動
cd public

# PythonのHTTPサーバーを使用
python3 -m http.server 8000

# または、npx serveを使用
npx serve .
```

ブラウザで `http://localhost:8000` にアクセスしてください。

## 機能詳細

### タグ検索機能

- **分類別カラーリング**: タグは4つの分類に分かれて色分けされています
  - **生成手法**（ブルー）: ジェネラティブ、確率的、パターン
  - **データタイプ**（グリーン）: 時系列、データ可視化、生活データ
  - **表現要素**（オレンジ）: 幾何学、記号・文字、線、点、色彩
  - **空間・配置**（パープル）: 空間配置、関係性、スケーリング、順序性

- **マルチタグ検索**: 複数のタグを選択してAND検索が可能

### パフォーマンス最適化

- **Lazy Loading**: Intersection Observer APIを使用した画像の遅延読み込み
- **無限スクロール**: 30件ずつ自動読み込み
- **CSS最適化**: `will-change`と`contain`プロパティによるレンダリング最適化

### アクセシビリティ

- 適切なARIAラベル
- キーボードナビゲーション対応
- スクリーンリーダー対応
- セマンティックHTML

## ブラウザサポート

- Chrome（最新版）
- Firefox（最新版）
- Safari（最新版）
- Edge（最新版）

## ライセンス

MIT
