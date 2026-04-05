# yoshida-kd.github.io

コーヒーブレイクの営業状況を表示するサイトです。

- **`index.html`** — 一般公開ページ。本日の営業状況と今月・来月のカレンダーを表示します。
- **`schedule.html`** — 管理者用ページ。パスワードで保護されており、日付をクリックして「営業日」「臨時休業」を切り替えられます。スケジュールは GitHub Gist に保存されます。

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

## パスワードのリセット方法

予定管理ページ（`schedule.html`）のパスワードを忘れた場合は、ブラウザの「LocalStorage」を消去することでリセットできます。

### 手順（Chrome の場合）
1. 予定管理ページを開く
2. F12（開発者ツール）を開く
3. **Application** タブ → **Local Storage** → 対象のオリジンを選択
4. `schedulePasswordHash` を右クリックして **Delete** する
5. ページをリロードすると初回設定画面が表示されます
