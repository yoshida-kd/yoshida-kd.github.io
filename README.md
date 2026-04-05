# yoshida-kd.github.io

## パスワードのリセット方法

予定管理ページ（`schedule.html`）のパスワードを忘れた場合は、ブラウザの「LocalStorage」を消去することでリセットできます。

### 手順（Chrome の場合）
1. 予定管理ページを開く
2. F12（開発者ツール）を開く
3. **Application** タブ → **Local Storage** → 対象のオリジンを選択
4. `schedulePasswordHash` を右クリックして **Delete** する
5. ページをリロードすると初回設定画面が表示されます
