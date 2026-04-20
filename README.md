# yoshida-kd.github.io

コーヒーブレイク（毎日15時〜17時）の営業状況を確認できるサイトです。

## ファイル構成

- **`office_hour/index.html`** — 一般公開ページ。本日の営業状況と今月・来月のカレンダーを表示します。
- **`office_hour/schedule.html`** — 管理者用ページ。パスワードで保護されており、日付をクリックして「営業日」「臨時休業」を切り替えられます。スケジュールは GitHub Gist に保存されます。

---

## GitHub PAT の設定

スケジュールを Gist に保存するには **Classic PAT**（`ghp_` で始まるもの）が必要です。

> ⚠️ **Fine-grained PAT は Gist をサポートしていません。** `github_pat_` で始まるトークンは使用できません。

### Classic PAT の作成手順

1. [https://github.com/settings/tokens/new](https://github.com/settings/tokens/new) を開く
2. **Note**（メモ）に適当な名前を入力（例: `coffee-break-gist`）
3. **Expiration**（有効期限）を設定
4. **Select scopes** で **`gist`** にチェックを入れる
5. **Generate token** をクリックしてトークンをコピー
6. `schedule.html` を開き、右上の **PAT設定** ボタンからトークンを登録

---

## パスワードについて

管理者用ページ（`schedule.html`）はパスワードで保護されています。パスワードはソースコード内に SHA-256 ハッシュとして固定されています。

パスワードを変更するには、`schedule.html` の `FIXED_PASSWORD_HASH` の値を新しいパスワードの SHA-256 ハッシュに書き換えてください。

```bash
echo -n "新しいパスワード" | sha256sum | cut -d" " -f1
```

