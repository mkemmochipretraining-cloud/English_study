# English_study

英語の文法・フレーズ・単語の知識を集約するリポジトリ。
学習用の Web アプリ（ブラウザだけで動作）と、Markdown の学習ノートで構成されています。

## Current Level
- TOEIC 660
- 日常会話はある程度可能
- 文法・語彙の基盤を再構築し、リスニング/スピーキング力を向上させる

---

## Apps（リンク）

| アプリ | リンク | 内容 |
|---|---|---|
| **English Training** | **https://mstk13.github.io/English_study/training.html** | HelloTalk メモ・文法ライティング・業務英語・語彙フラッシュカード |
| **Grammar Quiz** | **https://mstk13.github.io/English_study/index.html** | 6週間の文法クイズ（時制・関係詞・仮定法など） |

- インストール不要。スマホの Chrome / Safari でリンクを開くだけで使えます。
- iPhone なら Safari の「共有 → ホーム画面に追加」、Android なら Chrome の「ホーム画面に追加」で、アプリのように起動できます。
- **データはすべて端末のブラウザ内（localStorage）に保存されます。** サーバーには何も送信されません。ブラウザのデータを消すと記録も消えるため、定期的に **Export** でバックアップしてください。

---

## English Training の機能

画面下のタブで 6 つの画面を切り替えます。

### 1. Today — ダッシュボード
- 今日の進捗（Grammar / Writing / Vocab / **Memo** / Entries）を一覧表示
- 7 日間のストリーク（学習した日が緑になる。HelloTalk メモを 1 件書いた日もカウント）
- Quick Start ボタンから各機能へ直行
- 「Today's Activity」に、その日書いた英作文と HelloTalk メモが並ぶ

### 2. Memo — HelloTalk メモ（記録機能）
HelloTalk で教えてもらった単語・フレーズを、その場でメモして記録に残す機能です。

**記録する項目**

| 項目 | 内容 |
|---|---|
| 単語 / フレーズ (English) | 教えてもらった表現（必須） |
| 意味 (日本語) | 日本語訳 |
| 例文 / 実際に言われた文 | 相手が実際に使った文をそのまま残せる |
| メモ | ニュアンス、フォーマル度、似た表現など |
| 種類 | Word（単語）／ Phrase（フレーズ）／ Correction（直された表現）／ Slang（カジュアル表現） |
| 相手 / 場面 | 誰との会話で出てきたか（例: `Anna (US)`） |
| 日付 | 既定は当日。後からまとめて入力する場合は変更可 |

**できること**

- **追加 / 編集 / 削除** — 「+ Add」から追加、各メモの `Edit` / `Del` で修正・削除
- **★ スター** — 覚えにくい表現に印を付ける。復習カードで優先的に出題される
- **検索・絞り込み** — 英語・日本語・例文・メモ・相手名を横断検索。種類別／スター付きのみの表示も可能
- **日付ごとのグルーピング** — 新しい日付順に並び、いつ習った表現かが一目で分かる
- **AI 補完（任意）** — 単語だけ入れて「AI で意味・例文・ニュアンスを補完」を押すと、Claude API が日本語訳・例文・ニュアンス解説・種類を自動入力。会話中に単語だけメモしておき、後からまとめて肉付けする使い方ができます（利用には API Key の設定が必要）
- **Review as Cards** — 記録したメモをそのままフラッシュカードにして復習（下記 Vocabulary 参照）
- **Markdown 出力** — `Copy as Markdown` / `Download .md` で、リポジトリの `vocabulary/words.md`・`phrases/notes.md` と同じ書式のテキストを出力。貼り付ければ、そのまま Git 管理の学習ノートに残せます（表示中の絞り込み結果がそのまま出力されます）

出力される Markdown の例:

```markdown
## Phrase (フレーズ)

### Long time no see
- **意味**: 久しぶり
- **場面**: HelloTalk / Anna (US)
- **例文**: Hey, long time no see! How have you been?
- **メモ**: カジュアル。フォーマルな場では It's been a while. を使う。
- **記録**: 2026-08-27 (HelloTalk / フレーズ / Anna (US))
```

### 3. Grammar — 文法ライティング
- 文法トピック（現在完了 / 仮定法 / 関係詞 など）の解説と例文を表示
- そのトピックを使って英作文を 5 文書く
- `Save` で保存、`Save & Grade` で Claude API による自動採点（点数・添削・良かった点・改善点・模範解答）

### 4. Writing — 業務英語ライティング
- 進捗報告、レビュー依頼、設計の説明などのシナリオを選んで英文を書く
- こちらも `Save & Grade` で自動採点

### 5. Vocab — 語彙フラッシュカード
- タップで意味と例文を表示 → `Hard` / `OK` / `Easy` で自己評価
- 評価に応じて出題頻度が変わる簡易 SRS（間違えた語ほど早く再出題）
- **Deck 切替**:
  - `All` — 内蔵単語 + HelloTalk メモ
  - `Built-in only` — 内蔵の日常・技術・ビジネス語彙のみ
  - `HelloTalk Memo only` — 自分で記録したメモだけを復習
- スターを付けたメモは優先的に出題されます

### 6. Log — 学習ログ
- 過去に書いた英作文を日付順に閲覧、種類別に絞り込み
- 後からでも `Grade` ボタンで採点、`Del` で削除

### 共通機能
- **Export / Import** — 学習データ（英作文・**HelloTalk メモ**・語彙の習熟度・文法の進捗）を JSON でバックアップ／復元。機種変更時もこれで引き継げます
- **API Key** — 採点機能と AI 補完に使う Claude API キーを設定。キーは端末のブラウザにのみ保存され、Anthropic の API 以外には送信されません。**未設定でもメモ・英作文の記録機能はすべて使えます**（採点と AI 補完だけが無効）

---

## Grammar Quiz の機能
- 6 週間分の文法単元（時制 / 関係代名詞・受動態 / 仮定法・分詞構文 / 比較・冠詞 / 前置詞・動名詞 / 接続詞・総復習）
- 週ごとのタブと進捗バー
- 空欄補充・書き換えの練習問題に解答すると、その場で正誤と解説を表示

---

## Structure

```
English_study/
├── plan.md              # 学習計画 (7/16〜8/31)
├── index.html           # Grammar Quiz アプリ
├── training.html        # English Training アプリ（HelloTalk メモ・文法・ライティング・語彙）
├── grammar/             # 文法ノート（6週分の教材 + notes.md）
├── vocabulary/          # 単語・技術英語（words.md に単語ログ）
├── phrases/             # 日常会話・ビジネスフレーズ（notes.md にフレーズログ）
└── listening/           # リスニング・シャドーイング記録
```

## 使い方の流れ（推奨）
1. HelloTalk で会話中、教えてもらった表現を **Memo** タブにすぐ記録（英語だけでも可）
2. 会話後に「AI で補完」で意味・例文・ニュアンスを埋め、必要なら手直しして保存
3. 翌日以降、**Vocab** タブの `HelloTalk Memo only` デッキで復習
4. 週末に `Copy as Markdown` で `vocabulary/words.md` / `phrases/notes.md` に追記してコミット

## Tools
- HelloTalk (会話実践)
- English Grammar in Use (Intermediate)
- 金のフレーズ / Anki (単語)
