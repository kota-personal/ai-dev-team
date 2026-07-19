# AI 開発チーム - 週報記録

## プロジェクト概要

- **プロジェクト名:** 週報記録
- **種類:** Web アプリ（フロントエンド + バックエンド）
- **技術スタック:** 未定

## チーム構成

| エージェント | ファイル | 役割概要 |
|---|---|---|
| PM | [agents/pm.md](agents/pm.md) | ユーザー窓口・仕様定義・チーム調整 |
| Designer | [agents/designer.md](agents/designer.md) | HTML モック作成・UI/UX 仕様定義 |
| Tech Lead | [agents/tech-lead.md](agents/tech-lead.md) | 技術設計・アーキテクチャ・コードレビュー |
| Engineer | [agents/engineer.md](agents/engineer.md) | Web アプリの実装 |
| QA | [agents/qa.md](agents/qa.md) | 品質検証・バグレポート |
| Security Reviewer | [agents/security-reviewer.md](agents/security-reviewer.md) | セキュリティ観点でのレビュー・脆弱性検証 |

## 開発フロー

```
User
 │
 │ 要件を伝える
 ▼
PM ──────────────────────────────────────────────────────────┐
 │                                                            │
 │ デザイン依頼                                               │ 完成報告
 ▼                                                            │
Designer                                                      │
 │                                                            │
 │ HTML モック作成完了                                        │
 ▼                                                            │
PM → User（モック確認）                                       │
 │                                                            │
 │ OK                                                         │
 ▼                                                            │
Tech Lead（技術設計）                                         │
 │                                                            │
 │ 実装指示                                                   │
 ▼                                                            │
Engineer（実装）◄──────────────────────┐                     │
 │                                      │ NG（修正依頼）      │
 │ 実装完了                             │                     │
 ▼                        ▼            │                     │
QA（機能検証） Security Reviewer ──────┘                     │
 │             （セキュリティ検証）                           │
 │ 両方 OK                                                    │
 └────────────────────────────────────────────────────────────┘
```

## 基本ルール

- **ユーザーへの直接連絡は PM のみ**が行う
- 各エージェントは自身の責務外の判断を独断で行わない
- 仕様に疑問がある場合は PM に確認を求める
- QA・Security Reviewer で NG が出た場合は Engineer へ差し戻し、解決後に再検証する
- モックのユーザー承認なしに実装フェーズに進まない
