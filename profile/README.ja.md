<div align="center">

[English](./README.md) | [한국어](./README.ko.md) | **日本語**

# WhatNow

### Something broke. What now?

**あなたのAIはそのバグを直せる。何が起きたのかを知りさえすれば。**

[ウェブサイト](https://whatnow.dev) · [プロジェクト提案書](../docs/PROPOSAL.md) · [ロードマップ](../docs/ROADMAP.md)

</div>

---

## Don't explain your bug. Copy the context.

AIがバグを直せないのは、賢くないからではない。
コンテキストがないからだ。

**WhatNowはAIのためのCtrl+Cだ。** 問題が起きたら、AIに必要なすべて — Git diff、スタックトレース、ログ、ターミナル履歴、環境情報、Docker、Kubernetes — を自動で収集し、AIが最も理解しやすい形にまとめる。コピー一回、ペースト一回、解決。

### Before

```text
バグ発生
  → AIに説明
  → 「ログを見せてください」
  → ログを貼り付け
  → 「application.ymlも見せてください」
  → 設定を貼り付け
  → 「最近変更したファイルも見せてください」
  → Git diffを貼り付け
  → 40分経過
```

### After

```text
バグ発生
  → Copy Context
  → Paste
  → 解決
```

---

## 動作イメージ

```text
WHAT HAPPENED

14:32:17  PaymentService.kt を変更
14:33:02  ./gradlew bootRun を実行
14:33:04  MongoDB 接続失敗
14:33:05  アプリケーション起動失敗

ROOT CAUSE

最新のコミットで MongoDB の認証設定が
変更されています。

[ Copy for Cursor ]  [ Copy for Claude ]  [ Copy for ChatGPT ]
```

私たちはAIではない。AIが最も好む形で事件を整理するプログラムだ。

> **Your AI is only as good as your context.**
