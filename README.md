## WebP / AVIF 画像変換タスクランナー (個人開発)
## 概要：Node.js, sharp, chokidar を使用した画像最適化ツールです。`Promise.all` による並列処理や、ファイル監視による作業自動化が可能です。

`jpg`, `jpeg`, `png` 画像を自動で検出・並行変換する、Node.jsベースの軽量タスクランナーです。  
実務でのWebパフォーマンス改善や、次世代フォーマット（WebP/AVIF）の圧縮率検証を目的に開発しました。

##  特徴

- **高速な並行処理**: `sharp` と `Promise.all` を採用し、画像の非同期・並列変換を実現。
- **リアルタイム監視 (`watch`)**: `chokidar` により `/src` ディレクトリを監視。画像追加・更新時に自動で `/dist` へ変換出力します。
- **書き込み安定性の担保**: `awaitWriteFinish` を設定し、ファイル書き込み完了を検知してから安全に処理を開始。
- **柔軟なカスタマイズ性**: コード調整により、AVIF変換や可逆/非可逆圧縮（Lossy/Lossless）の切り替え・検証が可能。

##  技術構成

- **Runtime**: Node.js (ES Modules)
- **Key Packages**:
  - [sharp](https://github.com/lovell/sharp) (画像処理・フォーマット変換)
  - [chokidar](https://github.com/paulmillr/chokidar) (ファイルシステム監視)
- **Development Method**: AI (Cursor) を活用したバイブコーディング

## 使い方

### 1. 依存パッケージのインストール
```bash
npm install

### 2. タスクランナーの起動
```bash
npm run webp