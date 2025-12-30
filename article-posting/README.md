# 記事投稿Bot

Qiita/note.comへの記事投稿を自動化するボット

## 概要

Zennで作成した記事をQiitaやnote.comに自動投稿する仕組みを提供します。異なるプラットフォームへの投稿を一元管理し、メタデータの自動変換に対応しています。

**重要**: このシステムは**投稿設定**（note.com/Qiita API連携）だけでなく、**記事作成**（AI生成、テンプレート、メタデータ変換）も含みます。

## 主な機能

### Phase 1: note.com連携（デバッグ環境）
- ✅ note.com API連携
- ✅ デバッグ環境でのテスト投稿機能
- ✅ **記事作成機能**: Zennリポジトリから記事を取得、メタデータ変換

### Phase 2: Qiita連携（本番環境、2026年アドベントカレンダー対応）
- ⬜ Qiita API連携
- ⬜ メタデータの自動変換（Zenn → Qiita）
- ⬜ 2026年アドベントカレンダー対応
- ⬜ **記事作成機能**: AI生成、テンプレート適用

### Phase 3: スケジュール管理、自動投稿
- ⬜ 投稿スケジュール機能
- ⬜ 定時自動投稿

## システム構成

```
article-posting-bot/
├── gas/                            # Google Apps Script コード
│   ├── main.js                     # メインスクリプト
│   ├── connectors/                 # API連携
│   │   ├── note-com-connector.js   # note.com API
│   │   └── qiita-connector.js      # Qiita API
│   ├── creators/                   # 記事作成機能（重要）
│   │   ├── article-generator.js    # AI生成
│   │   ├── metadata-converter.js   # メタデータ変換
│   │   └── template-manager.js     # テンプレート管理
│   ├── fetchers/                   # 記事取得
│   │   └── zenn-fetcher.js         # Zennリポジトリから取得
│   └── utils/                      # ユーティリティ
│       └── scheduler.js            # スケジュール管理
├── templates/                      # メタデータテンプレート
│   ├── note-com/                   # note.com用
│   └── qiita/                      # Qiita用
└── docs/                           # ドキュメント
```

**記事作成機能の詳細**:
- **Zennリポジトリ連携**: [nomuraya-articles/Zenn](../../nomuraya-articles/Zenn) から記事を取得
- **メタデータ変換**: Zenn形式 → note.com/Qiita形式
- **AI生成**: 記事の自動生成（Phase 2）
- **テンプレート適用**: プラットフォーム固有のフォーマット対応

## セットアップ手順

### 前提条件
- Node.js 18以上
- note.com API キー
- Qiita API キー
- clasp のインストール

```bash
npm install
npm run login  # Google認証
```

### 環境変数の設定

`.env` ファイルを作成し、以下のAPIキーを設定します：

```
NOTE_COM_API_KEY=your_note_com_api_key
QIITA_API_TOKEN=your_qiita_api_token
```

## 関連リポジトリ

- [nomuraya-articles](../../nomuraya-articles) - Zennリポジトリ（既存）
- [gas-framework](../gas-framework) - GAS共通ライブラリ (#29)

## ライセンス

MIT
