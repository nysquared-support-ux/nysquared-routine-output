# NY-squared Routine Output

夜間自走 Remote Trigger の出力を保存する公開リポジトリです。

## 構成

- `outputs/YYYY-MM-DD/` - 夜間生成 content (Spoke/TikTok/SEO等)
- `codex-targets/` - 朝集約 JSON (Codex CLI 実行用)
- `summaries/` - 朝統合レポート markdown
- `archive/` - 90日経過後アーカイブ

## 自動化フロー

```
夜間 Remote Trigger (22:13-08:13 JST 毎時)
  → outputs/YYYY-MM-DD/ に push
        ↓
朝 Remote Trigger (08:30 JST)
  → codex-targets/ + summaries/ に push
        ↓
ローカル Task Scheduler (08:45 JST)
  → git pull → Codex CLI 実行
  → logs/codex-morning-*.md 生成 (本サイトとは別 Repo)
```

## 関連プロジェクト

- ABCクリニック SEO: https://abc-clinic-info.pages.dev
- 退職代行 SEOサイト (構築予定)

## 運用ルール

- content は **NY-squared 著作物**
- 商用利用は NY-squared (代表 YOSHITATSU) の許可必須
- API key・OAuth token・個人情報は **絶対に commit しない**

## ライセンス

MIT License (メタ情報・スキーマのみ・content 自体は別ライセンス)
