# AI Dev Team

AI エージェントで構成された開発チームをあなたのプロジェクトにセットアップするツールです。

`/init-ai-dev-team` コマンドを実行するだけで、プロジェクトの種類や規模に合わせた開発チーム構成を `.claude/` ディレクトリに自動生成します。

## チーム構成

| エージェント | 役割 |
|---|---|
| PM | ユーザー窓口・仕様定義・チーム調整 |
| Designer | モック作成・UI/UX 仕様定義 |
| Tech Lead | 技術設計・アーキテクチャ・コードレビュー |
| Engineer | 実装担当 |
| Mobile Engineer | iOS / Android / クロスプラットフォームの実装 |
| QA | 品質検証・バグレポート |
| DevOps | インフラ・CI/CD・デプロイ管理 |
| Security Reviewer | セキュリティ観点でのレビュー・脆弱性検証 |
| Technical Writer | ドキュメント・API 仕様書・マニュアル作成 |
| Scrum Master | タスク管理・スプリント計画・進捗管理 |

プロジェクトの種類に応じて推奨エージェントが提示され、必要なメンバーだけを選んで構成できます。

## 対応プロジェクト種別

- Web アプリ（フロントエンド + バックエンド）
- フロントエンドのみ（静的サイト・SPA）
- バックエンド API のみ
- iOS アプリ（Swift / SwiftUI）
- Android アプリ（Kotlin / Jetpack Compose）
- クロスプラットフォームアプリ（Flutter / React Native など）
- CLI ツール
- その他（自由記述）

## インストール

```bash
curl -o ~/.claude/commands/init-ai-dev-team.md \
  https://raw.githubusercontent.com/kota-personal/ai-dev-team/main/commands/init-ai-dev-team.md
```

## 使い方

新しいプロジェクトのディレクトリで以下を実行します。

```
/init-ai-dev-team
```

対話形式でいくつか質問に答えるだけで `.claude/` ディレクトリと `CLAUDE.md` が生成されます。

```
質問 1／4  プロジェクト名を教えてください。
質問 2／4  どのような種類のプロジェクトですか？
質問 3／4  チームに参加させるエージェントを選んでください。
質問 4／4  使用予定の技術スタックがあれば教えてください。
```

## 生成されるファイル

```
your-project/
├── CLAUDE.md                  # プロジェクトの使い方ガイド
└── .claude/
    ├── AGENTS.md              # チーム全体の概要・開発フロー
    └── agents/
        ├── pm.md
        ├── designer.md
        ├── tech-lead.md
        ├── engineer.md
        └── ...（選択したエージェントのみ）
```

各エージェントファイルには **役割 / 責務 / できること / できないこと / アウトプット / 判断基準** が記載され、プロジェクトの種類・技術スタックに合わせた内容にカスタマイズされます。

## 開発フロー（例：Web アプリ）

```
User → PM → Designer（HTML モック）→ PM → User（確認）
                                              ↓ OK
                                         Tech Lead（技術設計）
                                              ↓
                                         Engineer（実装）
                                           ↓       ↓
                                          QA   Security Reviewer
                                           ↓       ↓
                                         （両方 OK）
                                              ↓
                                         PM → User（納品）
```

## セットアップ後の使い方

生成された `.claude/` を持つプロジェクトでは、PM に話しかけることから開発を始めます。

```
PM として動いてください。〇〇という機能を追加したいです。
```

## サンプル

[.claude/](/.claude/) ディレクトリに「週報記録」Web アプリ向けのサンプル構成が含まれています。生成後のイメージとして参考にしてください。

## 動作要件

- [Claude Code](https://claude.ai/code)
