# gdg-tokyo/web-assets

GDG Tokyo のイベントやウェブサイト、connpass ページ等で使用する写真や画像ファイルを GitHub Pages 経由でホストするためのリポジトリです。

## URLの構成規則
画像は `https://gdg-tokyo.github.io/web-assets/` をベースURLとして、リポジトリ内のパスを繋げることで配信されます。

### 例:
- **イベント用の画像:**
  - リポジトリ内パス: `events/2026/20260115-gemini/keith-stevens-500px.jpg`
  - URL: `https://gdg-tokyo.github.io/web-assets/events/2026/20260115-gemini/keith-stevens-500px.jpg`
- **登壇者（再利用あり）の画像:**
  - リポジトリ内パス: `speakers/googler/speaker-name-20260614.png` (※日付のサフィックスを付与)
  - URL: `https://gdg-tokyo.github.io/web-assets/speakers/googler/speaker-name-20260614.png`

## ディレクトリ構成
- `events/`: 各イベントで使用する画像アセット（スライド、バナー、会場写真など）を配置します。年ごと、イベントごとにディレクトリを分けて配置します。
  - **イベント単体のゲストスピーカー（LT登壇者など）のプロフィール写真**も、再利用の予定がない場合はこの配下のイベント用フォルダに入れてください。
  - 例: `events/2026/20260115-gemini/`
- `speakers/`: GDG関係者など、**今後も再利用する可能性が高いメンバー・スピーカー**のプロフィール画像を配置します。
  - 例: `speakers/gde/`
  - ※ 画像ファイル名には、アップロードした日付をサフィックスとして付与してください（例: `name-YYYYMMDD.png`）。

## 使い方（画像の追加手順）
1. 画像を適切なディレクトリに配置します。
   - イベント用画像 / 単発のゲストスピーカー画像: `events/[年]/[日付-イベント名]/` の配下に配置してください。
   - 再利用のある登壇者用画像: `speakers/[カテゴリ（gde/googlerなど）]/` の配下に、ファイル名末尾にアップロード日を付与して配置してください。 (例: `name-20260614.png`)
2. 変更をコミットし、GitHubのデフォルトブランチ（`main` 等）にプッシュします。
3. プッシュ後、GitHub Pages のビルドが完了すると、上記のURL形式で画像にアクセスできるようになります。
