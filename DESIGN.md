---
name: AI Image Portfolio
version: alpha
description: 生成AIポートフォリオ（AI漫画・キャラクター・SNS画像制作）のUIデザインシステム。ダークな"スタジオ/ギャラリー"基調で作品を主役にする。
colors:
  bg:            "#0b0d12"   # ページ最下層（最暗）
  surface:       "#14171f"   # カード面
  surface2:      "#1b1f29"   # 一段持ち上げた面（hover/nav）
  fg:            "#eef0f4"   # 本文（AA: 対bg 15:1）
  muted:         "#9aa3b2"   # 補足テキスト（AA: 対bg 7.4:1）
  accent:        "#8aa2ff"   # 主アクセント（indigo）リンク・ボーダー
  accentInk:     "#0b0d12"   # accent上の文字
  gold:          "#ffcf6b"   # 強調・バッジ
  goldInk:       "#1a1305"   # gold上の文字
  line:          "#262b36"   # 罫線・境界
  good:          "#5fd0a0"   # 「商用可」等ポジティブ
typography:
  display:
    fontFamily: "'Outfit', 'Zen Kaku Gothic New', sans-serif"
    fontSize: 44px
    fontWeight: 700
    lineHeight: 1.18
    letterSpacing: -0.02em
  h2:
    fontFamily: "'Outfit', 'Zen Kaku Gothic New', sans-serif"
    fontSize: 24px
    fontWeight: 600
    lineHeight: 1.3
    letterSpacing: -0.01em
  h3:
    fontFamily: "'Zen Kaku Gothic New', sans-serif"
    fontSize: 16px
    fontWeight: 600
    lineHeight: 1.4
  body:
    fontFamily: "'Zen Kaku Gothic New', sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.75
  caption:
    fontFamily: "'Zen Kaku Gothic New', sans-serif"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.5
rounded:
  sm: 8px
  md: 12px
  lg: 18px
  pill: 999px
spacing:
  1: 4px
  2: 8px
  3: 12px
  4: 16px
  5: 24px
  6: 32px
  7: 48px
  8: 72px
components:
  button-primary:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.accentInk}"
    rounded: "{rounded.pill}"
    padding: 12px 22px
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.fg}"
    rounded: "{rounded.pill}"
    padding: 12px 22px
  chip:
    backgroundColor: "{colors.surface2}"
    textColor: "{colors.muted}"
    rounded: "{rounded.pill}"
    padding: 6px 14px
  card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.fg}"
    rounded: "{rounded.lg}"
  badge:
    backgroundColor: "{colors.gold}"
    textColor: "{colors.goldInk}"
    rounded: "{rounded.sm}"
    padding: 2px 10px
---

## Overview

生成AIで作った作品を売るためのポートフォリオサイト。**主役は画像、UIは黒子**。
深いダーク背景に作品を浮かび上がらせる「写真ギャラリー／スタジオ」の雰囲気。装飾は最小、余白を広く取り、
作品サムネのコントラストと一貫性で「この人に頼めば揃う」と一目で伝える。密度は中（情報過多にしない）。

トーン：プロフェッショナル・落ち着き・信頼。誇張やネオンは使わない。アクセントは indigo を点で、gold をバッジで。

## Colors

| トークン | 用途 |
|---|---|
| `bg` | ページ背景（最暗）。作品を最も引き立てる |
| `surface` / `surface2` | カード面 / hover・ナビ・チップ面 |
| `fg` / `muted` | 本文 / 補足。muted も bg 上で AA 7.4:1 を満たす |
| `accent`(indigo) | リンク・フォーカスリング・主ボタン・カードhover枠 |
| `gold` | セクションバッジ・数値ハイライトのみ（多用しない） |
| `good` | 「商用可・透かしなし」等の安心訴求 |
| `line` | 1px 罫線。影は控えめに、境界は線で表現 |

避ける：ピュアブラック#000・ピュアホワイト#fff、彩度の高いネオン、複数原色の同時使用。

## Typography

- 見出しは `Outfit`（ラテン）＋`Zen Kaku Gothic New`（和文）。本文・キャプションは `Zen Kaku Gothic New`。
- スケール：display 44 / h2 24 / h3 16 / body 14 / caption 12。行間は本文 1.75 でゆったり。
- 数字（点数・モデル数）は太く大きく見せて実績感を出す。

## Layout

- コンテンツ最大幅 1200px、中央寄せ。セクション間は spacing.8（72px）で大きく区切る。
- ギャラリーは `auto-fill, minmax(240px,1fr)` のレスポンシブグリッド、gap は spacing.5。
- 主役デモ（漫画・サムネ）は `auto-fit, minmax(320px,1fr)` の大判 2〜3 カラム。
- モバイルは 1 カラムに自然に畳む。タッチターゲットは最小 44px。

## Elevation & Depth

- 影は最小限。基本はフラット＋`line` の 1px 境界で面を分ける。
- hover 時のみ `translateY(-4px)` と淡い影、`accent` 枠で浮き上がりを表現。
- ライトボックスのオーバーレイは bg を 92% 不透明＋blur で背景を沈める。

## Shapes

- 角丸は rounded スケールを使用（カード lg=18px、チップ/ボタン pill、バッジ sm）。
- 画像カードは角丸でクリップ。グリッド作品は 1:1 にトリミング、デモ作品は元比率を維持。

## Components

- **button-primary**：CTA（相談ボタン）。pill・indigo・濃いインク文字。
- **button-ghost**：副次アクション。透明＋`line` 枠、hover で surface2。
- **chip**：ヒーローの実績スタッツ／フィルタ。pill・surface2。選択中フィルタは accent。
- **card**：作品カード。surface・rounded.lg・hover で持ち上げ＋accent枠。
- **badge**：セクション見出しの種別ラベル。gold・小。
- **lightbox**：カード画像クリックで全画面表示。ESC・背景クリック・×で閉じ、←→で前後移動。

## Do's and Don'ts

**Do**
- 作品画像を最優先で大きく・高コントラストで見せる
- 余白を恐れない。1セクション1メッセージ
- フォーカスリング・alt・reduced-motion 対応でアクセシブルに
- gold は「バッジ」と「数値」だけに限定して効かせる

**Don't**
- 背景にネオングラデを敷き詰めて作品を邪魔しない
- 原色を複数同時に使わない／文字を画像に直貼りして可読性を落とさない
- アニメーションを過剰にしない（prefers-reduced-motion を尊重）
- muted より薄い文字色を本文に使わない（AA 割れ防止）
