# はじめに

## 前提条件

開発を始める前に、以下がインストールされていることを確認してください：

- **Rust**: バージョン1.70.0以上
- **Git**: バージョン管理システム
- **テキストエディタ**: VS Code、IntelliJ IDEA、またはお好みのエディタ

## Rustのインストール

### Linux / macOS

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### Windows

[rustup-init.exe](https://rustup.rs/)をダウンロードして実行してください。

### インストールの確認

```bash
rustc --version
cargo --version
```

## プロジェクトのセットアップ

### 1. リポジトリのクローン

```bash
git clone <repository-url>
cd 241118_rust
```

### 2. 依存関係のインストール

```bash
cargo build
```

このコマンドは、`Cargo.toml`に記載されているすべての依存関係をダウンロードしてコンパイルします。

### 3. プロジェクトの実行

```bash
cargo run
```

## 開発ツール

### おすすめのエディタ拡張機能

#### VS Code
- **rust-analyzer**: Rust言語サポート
- **CodeLLDB**: デバッグサポート
- **crates**: Cargo.tomlの依存関係管理

#### IntelliJ IDEA
- **Rust Plugin**: 包括的なRustサポート

### コードフォーマット

プロジェクト全体をフォーマットする：

```bash
cargo fmt
```

### リンターの実行

コードの品質チェック：

```bash
cargo clippy
```

### テストの実行

すべてのテストを実行：

```bash
cargo test
```

特定のテストを実行：

```bash
cargo test test_name
```

詳細な出力でテストを実行：

```bash
cargo test -- --nocapture
```

## 基本的なワークフロー

### 1. 新機能の開発

```bash
# 新しいブランチを作成
git checkout -b feature/new-feature

# コードを編集
# ...

# テストを実行
cargo test

# コードをフォーマット
cargo fmt

# Clippyでチェック
cargo clippy

# 変更をコミット
git add .
git commit -m "feat: 新機能の追加"

# プッシュ
git push origin feature/new-feature
```

### 2. デバッグ

デバッグビルドで実行：

```bash
cargo run
```

詳細なログを有効にする場合（環境変数を使用）：

```bash
RUST_LOG=debug cargo run
```

### 3. リリースビルド

最適化されたビルドを作成：

```bash
cargo build --release
```

実行ファイルは`target/release/`に生成されます。

## よくある問題と解決方法

### コンパイルエラー

エラーメッセージを注意深く読んでください。Rustのコンパイラは非常に親切なエラーメッセージを提供します。

### 依存関係の問題

依存関係をクリーンビルドする：

```bash
cargo clean
cargo build
```

### パフォーマンスの問題

リリースモードでビルドしてください：

```bash
cargo build --release
cargo run --release
```

## 次のステップ

- [ARCHITECTURE.md](./ARCHITECTURE.md)でプロジェクトの構造を理解する
- [CONTRIBUTING.md](../CONTRIBUTING.md)で貢献ガイドラインを確認する
- [Rust公式ドキュメント](https://doc.rust-lang.org/)でRustについて学ぶ

## サポート

質問や問題がある場合は、GitHubのIssueを作成してください。
