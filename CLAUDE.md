# ムームーレインボー ホテル配送エリアマップ

## プロジェクト概要
- クライアント: ムームーレインボー（🔵 単発依頼）
- 用途: ハワイ・ワイキキ店舗（2270 Kalakaua Ave #1105）からのホテル配送エリア可視化
- 公開先: WordPress（muumuurainbow.jp）にショートコード `[muumuu_hotel_map]` で埋め込み
- 担当者: 菅谷さん
- Chatwork ルームID: 49278771 / 55873554 / 189041152
- 詳細クライアント情報: `~/ai-management/00_context/memories/clients/ムームーレインボー.md`

## 配送エリアの定義
| エリア | 範囲 | 料金 |
|--------|------|------|
| A | 店舗から半径約500m（ワイキキ中心部・徒歩10分圏） | 基本料金 |
| B | A圏外〜半径約2km強（アラモアナ・西部ワイキキ・カピオラニ公園周辺） | +$40 |
| C | それ以遠（カハラ・ダイヤモンドヘッド方面） | +$50 |

- A境界: 同心円 500m（2026-05-19 800m → 500m に縮小）
- 東側5件は B エリアへ移動済（2026-05-18）

## 構成ファイル
- `index.html` — 単体プレビュー用（Leaflet で地図描画）
- `wp-page-embed.html` — WordPress 固定ページへの埋め込み用HTML
- `hotel-list.md` — A/B/C エリア別ホテル一覧（マスタ）

## 関連プロジェクト
ムームー関連には以下の独立プロジェクトもある：
- `~/muumuu-pkhawaii/` — PKハワイ日本ECサイト（Shopify Dev MCP使用・Private repo）
- muumuurainbow.jp 本体・wiki-rental.muumuurainbow.com 等のWP保守

## Elementor 警戒（muumuu系の重要ルール）
muumuurainbow.jp および関連サイト（wiki-rental.muumuurainbow.com / .com/tryon / f.muumuurainbow.com）は **Elementor / Elementor Pro 使用**。

- **Elementor 自動更新ONはサイトを壊すリスクあり** → 「とりあえず更新しましょう」と勧めない
- 一方で放置すると依存プラグインとの互換性で決済ページが壊れる（2026-05-18 wiki-rental.muumuurainbow.com/checkout が真っ白になった）
- 「決済真っ白・フォーム描画されない」症状は Stripe・WooCommerce より先に **Elementor の更新状態を疑う**
- Elementor 更新を勧める前にれいちゃんに必ず確認

## GitHub Issue 管理
- Issue は `reiko-panthers/ai-management` に作る
- タイトル形式: `【ムームーレインボー】依頼内容（期日YYYYMMDD）`
- プロジェクトラベルは付けない（タイトル先頭で識別）

## 機密情報
- WP管理画面のパスワード等は **1Password で管理**。.md ファイルには書かない

## グローバル共通ルール
全プロジェクト共通の汎用ルール（メール書式・CC引き継ぎ・Git運用・デザイン・機密・画像生成等）は `~/.claude/CLAUDE.md` 参照。
