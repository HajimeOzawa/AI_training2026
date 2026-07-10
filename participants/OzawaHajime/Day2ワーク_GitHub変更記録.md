# Day2ワーク：研修リポジトリで変更を記録する


## このワークのゴール
研修リポジトリの**自分のフォルダ**で、`feat/氏名` ブランチを切り、変更を commit する。
「作業を分ける（ブランチ）→変更を記録する（commit）」を、Git操作は Claude に任せながら体験する。



## 準備0：GitHub にログインする（初回のみ）
> ※ 研修リポジトリは **private** です。clone / push には GitHub 認証が必須。一度ログインすれば以降は不要。

ターミナルで以下を実行し、**ブラウザ認証**でログインします（対話ターミナル前提）。

```bash
gh auth login
```

- 選択肢は `GitHub.com` →（HTTPS）→ `Login with a web browser` を選ぶ。
- 画面に表示されるワンタイムコードを控え、自動で開くブラウザに貼り付けて認証。
- 認証確認： `gh auth status` で `Logged in to github.com` と出ればOK。
- `gh` が未インストールの場合は `brew install gh`（Mac）。


## 準備1：研修リポジトリを clone する（初回のみ）
> ※ 一度 clone すれば2回目以降は不要。すでにフォルダがある人はSTEP1へ。

作業したい場所（例：デスクトップや任意の作業フォルダ）で、リポジトリを手元に複製します。

```bash
# HTTPS（推奨）
git clone https://github.com/honda-hm-rd/AI_training2026.git

# もしくは SSH（SSH鍵を登録済みの人）
git clone git@github.com:honda-hm-rd/AI_training2026.git
```

- 実行すると `AI_training2026` フォルダが作成されます。
- `Repository not found` / 認証を求められる → **準備0のログインが未完了**。`gh auth login` を先に実施。
- `Permission denied (publickey)`（SSH選択時）→ SSH鍵が未登録。上のHTTPSを使う。
- clone がうまくいかない場合は Claude に依頼してもOK。
> 「`https://github.com/honda-hm-rd/AI_training2026.git` を clone して。」


## 進行手順（当日＝ここまで全員）
### STEP1：自分のフォルダへ移動
下記cd以下をターミナルで実行
```bash
cd AI_training2026
mkdir -p participants/<自分の氏名>
cd participants/<自分の氏名>
claude    # まだ起動していなければ
```

```bash
cd AI_training2026
mkdir -p participants
cd participants
mkdir <自分の氏名>
cd <自分の氏名>
claude    # まだ起動していなければ
```

### STEP2：ブランチを作って切り替える※Claudeに任せてOK
> 「`feat/<自分の氏名>` というブランチを作って切り替えて。」

### STEP3：変更して commit する（5分）
1. 自分のフォルダでファイルを1つ変更（メモ作成など）。
2. > 「今の変更をステージして、日本語の簡潔なメッセージで commit して。」

### STEP4：履歴を確認する（2分）
```bash
git log --oneline
```
- 自分の変更が1件記録されていることを確認。

## 【手順書パート】push → PR（各自／時間があれば）
> ※ 当日のワークはSTEP4まで。ここから先は**環境が通る人・時間がある人**が各自進める（先方GitHubの認証・プロキシ次第）。

### STEP5：リモートへ push する
> 「このブランチをリモートに push して。」
```bash
git push -u origin feat/<自分の氏名>
```

### STEP6：Pull Request を作成する
- GitHub 上で `feat/氏名` → `main` の Pull Request を作成し、変更を共有する。
> 「今のブランチから main への Pull Request を作成して。タイトルと概要も付けて。」

## 完了の目安
- `feat/氏名` ブランチで自分の変更が commit され、`git log` に出る。



