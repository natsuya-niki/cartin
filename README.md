# 自動でカートに入れる

## 環境構築

### 前提条件
- [Homebrew](https://brew.sh/ja/)がインストールされていること

### 必要なツールのインストール
1. nodenvのインストール
   ```bash
   brew install nodenv
   echo 'eval "$(nodenv init -)"' >> ~/.zshrc  # zshの場合
   source ~/.zshrc
   ```

2. pnpmのインストール
   ```bash
   brew install pnpm
   ```

### セットアップ手順

1. nodenvで指定のNode.jsバージョンをインストール
   ```bash
   # Node.jsのバージョンを設定
   nodenv local $(cat .node-version)
   # => 22.7.0

   # nodenvの初期化（新しいシェルを開いた場合に必要）
   eval "$(nodenv init -)"
   ```

2. 依存関係のインストール
   ```bash
   pnpm install
   ```

3. Playwrightのブラウザをインストール
   ```bash
   pnpm exec playwright install
   ```

4. 環境変数の設定
   ```bash
   cp .env.sample .env
   # .envファイルを編集して必要な認証情報を設定してください
   ```

## 実行方法

```bash
pnpm exec playwright test tests/matsukiyo.spec.ts --project=chromium --headed
```
