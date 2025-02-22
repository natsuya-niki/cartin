# 自動でカートに入れる

## 環境構築

### 前提条件
- [nodenv](https://github.com/nodenv/nodenv)がインストールされていること
- [pnpm](https://pnpm.io/ja/)がインストールされていること

### セットアップ手順

1. nodenvで指定のNode.jsバージョンをインストール
   ```bash
   nodenv install $(cat .node-version)
   nodenv local $(cat .node-version)
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
cp .env.example .env
# .envファイルを編集して必要な認証情報を設定してください
```

## 実行方法

```bash
pnpm exec playwright test tests/matsukiyo.spec.ts --project=chromium --headed
```
