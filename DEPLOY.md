# GitHub Pages デプロイ手順

## 前提
- GitHubアカウントを新規作成済み
- デプロイ対象フォルダ：`e:\ObsRepo\brainbox\brainbox\Note\Nisa50`

## フォルダ構成

```
Nisa50/
├── index.html          ← ポータルページ（3ツールへの導線）
├── robots.txt          ← 検索エンジンブロック
└── portfolio/
    └── index.html      ← パスワードゲート付きポートフォリオ設計シート
```

## 手順

### 1. GitHubでリポジトリを作成
1. https://github.com/new を開く
2. **Repository name**: `nisa50-tools`（任意。URLの一部になる）
3. **Public** を選択（GitHub Pages無料版はPublicのみ）
4. 「Create repository」をクリック

### 2. ローカルでGit初期化＆Push

```powershell
cd e:\ObsRepo\brainbox\brainbox\Note\Nisa50

git init
git add .
git commit -m "初回コミット：ポートフォリオ設計シート"
git branch -M main
git remote add origin https://github.com/【あなたのユーザー名】/nisa50-tools.git
git push -u origin main
```

※ 初回pushでGitHub認証を求められます。ブラウザ認証またはPersonal Access Tokenで認証してください。

### 3. GitHub Pagesを有効化
1. GitHubでリポジトリページを開く
2. **Settings** → **Pages** を開く
3. **Source**: 「Deploy from a branch」を選択
4. **Branch**: `main` / `/ (root)` を選択
5. 「Save」をクリック

### 4. 公開URLの確認

数分待つと以下のURLで公開されます：

```
https://【あなたのユーザー名】.github.io/nisa50-tools/
```

ポートフォリオ設計シートのURL：
```
https://【あなたのユーザー名】.github.io/nisa50-tools/portfolio/
```

## パスワード情報

| 項目 | 値 |
|---|---|
| パスワード | `beee50nisa2026` |
| note記事への記載場所 | 有料エリアの末尾（特典案内セクション） |

### note記事への記載例

```
━━━━━━━━━━━━━━━━━━━━
🎁 購入者限定 3大特典
━━━━━━━━━━━━━━━━━━━━

以下のURLからツールにアクセスできます。
🔗 https://【URL】/nisa50-tools/

パスワード：5uto50nisa2026

【特典①】ポートフォリオ設計シート
  9項目を入力するだけで、あなたに最適な投資パターンと
  配分を自動診断します。

【特典②】iDeCo×退職金 受取シミュレーター（近日公開）
【特典③】暴落対応チェックリスト（近日公開）
```

## 更新方法

ファイルを修正したら：

```powershell
cd e:\ObsRepo\brainbox\brainbox\Note\Nisa50
git add .
git commit -m "更新内容の説明"
git push
```

数分で自動的に反映されます。
