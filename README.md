# Ranking - 統計カウント＆ランキングプラグイン

7種類のプレイヤー統計をカウントし、ランキング表示・看板表示・EmeraldBank連携報酬を提供するプラグインです。

---

## 機能

### 7種類の統計
- **採掘 (Mining)**: ブロック破壊数（クリエイティブ除く）
- **釣り (Fishing)**: 魚を釣った回数
- **設置 (Placing)**: ブロック設置数
- **食事 (Eating)**: 食料を食べた回数
- **討伐 (Killing)**: モンスター討伐数
- **レベル (Level)**: 現在の経験値レベル
- **与ダメージ (Damage)**: エンティティに与えた総ダメージ

### ランキングシステム
- 各統計タイプ別のランキング表示
- 看板に自動表示（単一順位または範囲1-4）
- 設定間隔で自動更新

### 報酬システム
- EmeraldBank連携で自動エメラルド付与
- 統計タイプごとに報酬レートを個別設定可能
- サウンド＆メッセージ通知

### データ管理
- 5分ごとの自動保存（設定変更可能）
- 毎月1日に自動リセット
- 前月データはアーカイブに保存

---

## コマンド

| コマンド | 説明 | 権限 |
|---------|------|------|
| `/ranking` | 自分の統計を表示 | `ranking.stats` |
| `/ranking stats [player]` | プレイヤーの統計表示 | `ranking.stats.others` |
| `/ranking ranking [type] [limit]` | ランキング表示 | `ranking.ranking` |
| `/ranking top [type] [limit]` | ランキング表示 | `ranking.ranking` |
| `/ranking setsign <type> <rank>` | ランキング看板設置 | `ranking.admin` |
| `/ranking removesign` | ランキング看板削除 | `ranking.admin` |
| `/ranking updatesigns` | 全看板を即座に更新 | `ranking.admin` |
| `/ranking reload` | 設定リロード | `ranking.admin` |
| `/ranking reset` | データリセット | `ranking.admin` |

**エイリアス:** `/rank`, `/miningrank`, `/mrank`

---

## 看板設置

1. `/ranking setsign <type> <rank>` を実行
   - 単一順位: `/ranking setsign mining 1`
   - 範囲指定: `/ranking setsign mining 1-3`（最大4人）
2. 対象の看板を右クリック
3. 看板にランキングが自動表示

---

## 権限

| 権限 | 説明 | デフォルト |
|------|------|-----------|
| `ranking.stats` | 自分の統計を表示 | true |
| `ranking.stats.others` | 他人の統計を表示 | op |
| `ranking.ranking` | ランキング表示 | true |
| `ranking.admin` | 管理者権限 | op |

---

## 報酬設定例
```yaml
rewards:
  mining:
    enabled: true
    actions-per-emerald: 20    # 20ブロック採掘で1エメラルド
    emerald-amount: 1
  fishing:
    enabled: true
    actions-per-emerald: 30    # 30回釣りで1エメラルド
    emerald-amount: 1
  killing:
    enabled: true
    actions-per-emerald: 50    # 50体討伐で2エメラルド
    emerald-amount: 2
```

---

## 依存関係

| プラグイン | 必須/任意 |
|-----------|----------|
| EmeraldBank | 必須 |

---

## 動作環境
- Spigot/Paper 1.21.x
- Java 17以上

## コミュニティ
**Discord:** https://discord.gg/zYY55dzhjd

## ライセンス
All Rights Reserved
