# CONTRIBUTING for jp

以下に挙げることさえ認知していただければ、基本なんでもOKです。

## アプリ・フォントの追加について

### 採用基準

採用にあたって以下の基準を設けています。

- `scoop bucket known`に挙げられるBucketで取り扱っていない
- 日本語を取り扱うことを目的に作られたアプリまたはフォントである
- バージョン番号が確認できる(アップデートが行われているもの限定)

### Manifestについて

追加希望の際、Manifestを自作してPull Requestという形で報告してくれると追加がスムーズになります。
この時、自動アップデート処理やテストが正常に通ることを確認してください。各スクリプトは当リポジトリのbinディレクトリ内にそれぞれ`checkver.ps1` `test.ps1`として格納されています。これらの動作はScoopのものに準じます。

なるべく余計なパスへの追加およびエイリアスや環境変数の設定は行いません。各公式がREADMEやチュートリアルなどにて推奨するものだけを設定します。
ただしパッチ済みアプリのように`scoop bucket known`にあるBucketとのコマンド競合が考えられるときに限り、専用のエイリアスやショートカットを設ける場合があります。(例: vim-kaoriya)

## アプリ・フォントの削除について

アプリまたはフォントの削除については、以下のいずれかを満たす場合のみ行います。

- 明らかなライセンス違反、規約違反である
- 作者本人による拒否または削除の意向が管理者から確認できる

ライセンス違反などのご報告はどなたからでも受け付けています。

## 動作報告について

原因や対処方法が明確でない限り、報告時にはなるべく以下の情報も付け加えてください。

- 実行コマンド
- 動作環境
- Scoop/Bucket/Manifestのバージョン

## フォントManifestについて

フォントのインストールおよびアンインストール処理はすべて`jp-util-font`Manifestを用い、可能な限り既存のフォントManifestと同一のものにしてください。

## スクリプトについて

psutilディレクトリに格納されるスクリプトはScoopでのインストール処理などで使われることを想定されているため、紐づくManifestが用意されている必要があります。
スクリプトの新規作成時や更新時には併せてManifestも適宜作成・編集を行ってください。対応するManifest名は`jp-util-(スクリプト名)`とします。(例: `font.ps1` → `jp-util-font`)
