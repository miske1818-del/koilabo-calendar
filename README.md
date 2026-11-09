# 恋ラボ イベントカレンダー

## iPhoneで無料公開する（GitHub Pages）
1. Safariで github.com にログインし、新しい **Public** リポジトリ `koilabo-calendar` を作る。
2. このZIPをiPhoneの「ファイル」で展開し、`index.html` と `events.json` をリポジトリのルートにアップロードする（GitHubのWeb画面が難しい場合はSafariの「デスクトップ用Webサイトを表示」）。
3. リポジトリの Settings → Pages → Build and deployment → Deploy from a branch → main / (root) → Save。
4. 数分後 `https://ユーザー名.github.io/koilabo-calendar/` で公開される。
5. LINE公式アカウントのリッチメニューAのアクションを「リンク」にして上記URLを貼る。

## iPhoneでイベントを追加・変更・削除
GitHubのリポジトリで `events.json` を開き、鉛筆アイコン（Edit this file）で編集 → Commit changes。変更は数分で公開ページに反映される。編集画面が出ない場合はSafariでデスクトップ用Webサイトに切り替える。

`events` 配列に以下のようなデータを追加する（日時は実際の開催予定に変更）。複数登録するときは `},` で区切る。削除するときは該当の `{ ... }` を消す。残席は予約状況に合わせて手動更新する。

```json
{
  "settings": {"lineUrl": "https://lin.ee/あなたの公式LINEリンク"},
  "events": [
    {
      "id": "event-001",
      "date": "2026-12-12",
      "title": "20〜30代 恋活パーティー",
      "start": "13:00",
      "end": "15:00",
      "place": "夜カフェ ibuki（岡山市）",
      "age": "20〜39歳",
      "malePrice": 4000,
      "femalePrice": 1500,
      "maleSeats": 5,
      "femaleSeats": 5,
      "description": "1対1トーク形式・初参加歓迎"
    }
  ]
}
```

**重要：** 上の日時・価格・残席は記入例であり、実際のイベントではありません。配布ファイルの `events.json` はイベント0件の状態です。

## LINE予約
`settings.lineUrl` にLINE公式アカウントの「友だち追加URL」（https://lin.ee/... など）を入力する。予約ボタンは予約内容をコピーしてLINEを開く方式。参加者はトークに貼り付けて送信する。iPhoneのブラウザによってコピーに失敗する場合は画面の案内に従い手入力する。**予約確定・残席更新は自動ではない**ため、スタッフが返信して手動で残席を更新する。

## 注意
- 公開GitHubリポジトリには個人情報、参加者の氏名・連絡先、パスワード、秘密情報を保存しない。
- GitHubアカウントのログイン情報は第三者に渡さない。
- サイトのカレンダーは現在の月を含む3ヶ月表示。翌月になると表示範囲は自動的に進む。
- `events.json` を手動で編集するため、JSONの記号を壊すと読み込みエラーになる。iPhoneだけでの運用は可能だが、管理画面付きサービスより操作は少し難しい。
