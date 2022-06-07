## アプリ概要・機能

HR/HMを中心とした音楽情報・交流サイトです。  


サイト名 : MetalSpace  
URL : https://www.metalspace.site/


- アートワーク画像一覧からアーティスト情報を探すことができます
![アーティスト一覧](https://github.com/ryo246912/portfolio/wiki/images/artists_v2_r1.gif)
  - 国・名前でのフィルタリング
  
  ![フィルタリング](https://github.com/ryo246912/portfolio/wiki/images/artists_filter.gif)
- アルバム・楽曲情報を一覧から調べることができます  
![アルバム一覧](https://github.com/ryo246912/portfolio/wiki/images/artworks.gif)
- アカウントを作成（Twitter認証によるログイン）することで、つぶやきを投稿することができます

### コンテンツ
- アーティスト一覧(国・名前でのフィルタリング)
- アーティストのアートワーク一覧
- アートワークの楽曲情報一覧

### つぶやき機能
- つぶやき機能
- 返信機能
- いいね機能 
- ハッシュタグ検索機能

### マイページ
- ログイン機能（Twitter認証）
- プロフィール編集機能（アイコン画像・テキスト）
- つぶやき一覧

---

## ポートフォリオとして

* HR/HMを中心とした音楽情報・交流サイトを作成しました。 
* 上記情報・画像を集めるために以下サイトからクローニング/スクレイピングをするプログラムも作成しました
    * [Musicbrainz](https://musicbrainz.org/) (音楽データベースサイト、ジャンル：全般)
    主に楽曲情報を取得
    * [Discogs](https://www.discogs.com/ja/) (音楽データベース・マーケットプレイスサイト、ジャンル：全般)
    主にアートワーク画像を取得
    * [Encyclopaedia Metallum](https://www.metal-archives.com/) (音楽データベースサイト、ジャンル：HMのみ)
    主にアートワーク画像を取得


## 使用技術

- フロントエンド
	- HTML
	- CSS (Tailwind CSS)
	- JavaScript
	- React (Next.js | MUI=旧Material-UI )
- バックエンド
	- Python (Django & DjangoRESTFramework)
- DB
  - PostgreSQL
- インフラ
  - Heroku
  - Vercel
  - AWS (S3)
- ツール
  - A5:SQL Mk-2 (SQLクライアント)
  - Draw.io (作図ツール)
  - REST Client (APIの検証)
- 開発環境
  - VSCode | WSL2
  - Git | GitHub
  - Docker & Docker-Compose

![アプリ構成図](https://github.com/ryo246912/portfolio/wiki/images/app.drawio.png)

## アプリを作成した理由
上記Webアプリを作成した理由は主に以下の3点です。  

### 1.閲覧しやすい音楽情報サイトが欲しかったため

  アーティストのアルバム・楽曲情報を調べる際に、既存サイトでは以下の点で使いずらさを感じていました。  
- 情報サイト(例.wikipedia)では、  
  文字情報が多く閲覧性がいまいちor昔のサイトではスマホ閲覧を想定したデザインでないことが多い
- 楽曲配信サイト(例.Spotify/Apple Music)では、  
配信非対応アーティスト・未配信楽曲などがあり、情報に抜けがある
- 検索エンジン(例.Google検索)では、  
検索ワードを入れて検索及び検索結果から目的の情報を探すのに手間がかかる

そのため、
- スマホ閲覧を想定(=レスポンシブ対応・閲覧性を意識したサイト)
- アーティスト楽曲情報を網羅的にまとめる
  
ことを意識しました。

### 2.アーティスト・楽曲について気軽につぶやき合う場が欲しかったため  
ネット上で好きなアーティスト・音楽について感想を言う・語り合う際に、  
既存の投稿・レビューサイト等では以下の点に不満を感じていました。
- SNS(例.Twitter)では、  
  タイムライン・トレンドを意識した設計のため、トレンドではない話題について語り合える機会が少ない
- レビューサイトでは、  
  つぶやくのに敷居があるため、気軽につぶやくことができない

そのため、
- アーティストページ上に投稿機能を設けることで、トレンドを意識せずに共通の話題について語り合える
- SNSライクな投稿機能を設ける  

ことを意識しました。

### 3.情報の蓄積・ストックを意識したサービスを作成したかったため

昨今の情報に対する触れ合い方を見て、以下の点に課題を感じていました。
  - トレンド・タイムリーな話題にフォーカスされることが多く、昔の話題について語り合える場が少ない
  - 多くのサービスが「今」を意識した設計であり、過去の情報が流れていきやすい

そのため、トレンド・タイムラインによらず昔の話題も語り合える  
そして過去の情報のストックを意識したサービスを設計したいと考えました。

## 使用技術の選定理由
- フロントエンド
  * React・Next.js
  主に以下の理由からReactを最初採用しました
      * SPAのような画面遷移体験がよく、手軽に情報を閲覧できるようにしたいサイトを作成したいと思ったため（その点で従来サイトとの差別化を図りたいと思ったため）
      * (将来的には)React Nativeによるクロスプラットフォームでの開発にも興味があったため

    その後以下の点に魅力を感じ、途中からNext.jsを採用して開発しました
      * ルーティング設定がファイル作成で手軽に行うことができる
      * 半分は情報サイトであり、毎回クライアント側でfetchするほど更新頻度が高くないこともあり、SSG機能に魅力を感じたため

  * MUI=旧Material-UI | Tailwind CSS
  正直デザイン面には苦手意識があるため、手軽にデザイン面をサポートしてくれるものとして、好みなデザインであるMaterial-UI(MUI)を採用しました
  その後、主にcssのclass命名に悩むことが多く、どうにかしたいと思った際に、あらかじめデザインに対応したclass名が設けられているTailwind CSSを見つけ、採用しました

* バックエンド
	* Django & DjangoRESTFramework
  主に以下の理由からPython/Djangoを採用しました
      * Webアプリ開発以前からPythonには触れていたため
      * データセットを集めるためのクローニング・スクレピングを行うにあたって、Pythonが第一候補としてよく挙げられていたため
      上記の技術選定については、以下記事に詳細を述べています
    [Djangoを選定した理由](https://zenn.dev/ryo246912/articles/6dd53f5fa4d29f)

* その他
  * Docker
  Docker含め、技術選定の観点として、
    * 利便性
    * 学習の環境
    * 該当技術のコミュニティの活発さ
  に加え、
    * 開発環境構築の容易さ・手軽さ
    * **他技術への移行容易性**
  
    を意識しています
    そのため、ローカル環境を汚さずライブラリ・開発環境を手軽に再現・破棄できるDockerを採用しました。
    (移行容易性を重視するきっかけとして、学生時代の経験があります。
  当時はWinXPで便利なソフトやショートカット等で設定をカスタマイズすることにハマっていたのですが、Win7に移行した際、互換性がなかったり、プレーンなPCでは操作性が落ちる等により、癖の強いカスタマイズや依存関係を持つことはその後の運用で苦労することを学びました。そのため、開発環境・ライブラリ・コード等においても癖のある設計・依存関係にならないようにする点を意識しています)


## 工夫した点

### 1. パフォーマンス改善

  1. 1+N問題解消
  今回のアーティスト・アートワークのDB設計は次のようになっています。
  ![DB設計](https://github.com/ryo246912/portfolio/wiki/images/ER01.jpg)
  アーティストの情報を取得する際に、合わせてアートワーク情報もJOINして一度にデータを取得したいのですが、特に意識しないと1+N問題が生じて、レスポンスが遅くなります。
  そのため、`django-debug-toolbar`や標準ログライブラリ発行SQLで確認しつつ、1+N問題を解消しました。

  1. 本番DBへのデータ登録のパフォーマンス改善
  クローニング・スクレイピングしたデータはデータチェック・加工する必要があることから、一度スクレイピング用DBに保存して、データチェックをしてからHerokuサーバ上の本番DBに登録しています。
  1アルバム・1楽曲毎にチェックしてデータ移行させるのは時間がかかりすぎる、だが一括に登録させる際にデータ重複させたくないとのことで、当初は1データずつデータの存在確認(`Model.objects.filter(key=value).exists()`=SQLを発行)をして実施していました。
  しかし、各データごとにHerokuDBへの問い合わせが発生し、データ登録時間がかかりすぎてデータ追加作業が現実的でないとのことで、登録ロジックを変えました。
  具体的には、
      * 一度必要データ分を全件手元に取得する→手元データ内で登録有無を確認(HerokuDBへの問い合わせが不要)
      * 通常IDとは別に各データにユニークキーのカラムを設ける
      * `bulk_create()`のオプション`ignore_conflicts=True`を使用する(データをSQL1件で一括登録できるかつユニークキーで重複がある場合はDBへの登録をしない)
  
      上記により、データの重複なしにアートワークが80程度あるアーティストの場合、登録時間を1/5以下(登録時間15分→3分)に抑えました

### 2. CROS(オリジン間リソース共有)
  今回SPA+APIを採用するにあたり、認証情報のやりとりにCookieによるセッション認証を採用しました
  API周りでの認証ではJWT等のトークン認証がよく紹介されていますが、下記理由により今回はセッション認証を採用しました
  * Tokenの保管先に議論の余地あり
  参考:[HTML5のLocal Storageを使ってはいけない（翻訳）](https://techracho.bpsinc.jp/hachi8833/2019_10_09/80851)
  * トークン認証の利点であるスレートレスによるスケーラビリティは、サイト立上当初において上記理由を上回るほどの利点ではない
  * 今回のAPIは特定のフロントエンドのバックエンドとしての役割のみであるため、スレートレスである点に大きなメリットがない
  
  Cookieによるセッション認証の場合、カスタムドメインでやり取りする際は設定をいじる必要があり、以下のようにしてやりとりしています。
  * バックエンドでのCookie(SessionID/CRSFToken)をサブドメインであるフロントエンドでも使用するために、`Domain=ルートドメイン`をセット
  * アーティスト・楽曲情報を返す一部APIはクライアント側には不要(フロントエンドがSSGする際にのみアクセス)であることからも、Cookieに認証キー`X-API-KEY`を設けてアクセスを制限

また、データをPOSTする際には`Content-Type: application/json`を設定し、PreflightリクエストにてCSRFトークンの検証をすること`request.headers: { x-csrf-token: 'ランダム文字列'}`ことでCSRF対策を実装しました

### 3. データセットの準備・確認

今回楽曲情報・画像データを準備・登録する際に、以下の点を工夫しました
  1. アートワーク画像の取得
  今回楽曲情報のメインは[Musicbrainz](https://musicbrainz.org/)を用いたのですが、アートワークは未登録なことが多いです。
  そのため、アートワーク情報は[Encyclopaedia Metallum](https://www.metal-archives.com/)を主に使用しましたが、使っていくうちにデータに抜けがあるに気が付きました。
     * 主にメタルがメインのサイトであるため、例えば
     Aerosmith・Bonjoviなどのハードロックバンドや
     Slipknot・Babymetalなどのモダンなメタルバンドは未登録である
     
     そのため、取得先としてアーティストのジャンル自体の専門性は設けていない[Discogs](https://www.discogs.com/ja/)の情報も活用し、補完することでデータを集めました。
     また、今回画像が比較的に多いサイトであることからも画像の大きさ・データサイズを意識して、サイズ:400×400以上、容量250KB以下になるように適宜画像を加工して揃えています。
  <br>
  1. 情報の登録ミス防止
  今回サイトを作成するにあたって、
     * HerokuDBには楽曲情報(アーティスト・アートワーク・楽曲情報・リリース日等)
     * S3にはアートワーク画像
  
     をアップロードする必要があります。
  スクレイピングしたDBには本番に採用しない情報(まだ現時点で追加しない・ブートレグなどオフィシャルデータでない・データ整備が未完了etc)も登録されており、それらを登録フラグを立てて管理しています。
  当初、登録フラグの管理ミス等でアートワークの楽曲情報が適切に登録されていないなどのミスがありました。そのためデータの登録ミスを防ぐために、確認メソッドを追加し、抜けがある場合はログ出力するようにしています。
  具体的な確認内容1例は以下です

```python
    @admin.action(description="Check:Record前チェック")
    def check_before_record(self,request,queryset):
        prefetch1 = Prefetch('musicbrainzartworkgroup_set', queryset=models.MusicbrainzArtworkGroup.objects.filter(prod=True), to_attr="musicbrainzartworkgroup_set_filter")
        prefetch2 = Prefetch('musicbrainzartworkgroup_set_filter__musicbrainzartwork_set', queryset=models.MusicbrainzArtwork.objects.filter(prod=True), to_attr="musicbrainzartwork_set_filter")
        prefetch3 = Prefetch('musicbrainzartworkgroup_set_filter__musicbrainzartwork_set_filter__musicbrainztrack_set', queryset=models.MusicbrainzTrack.objects.filter(prod=True), to_attr="musicbrainztrack_set_filter")

        for x in queryset.filter(prod=True).prefetch_related(prefetch1,prefetch2,prefetch3): 
            if x.country_code is None or x.year is None:
                logger.info(
                    "Admin:{0}:{1}確認してください".format(f"{x}のcountry未登録です" if x.country_code is None else None,f"{x}のyear未登録です" if x.year is None else None)
                )
            if True not in [y.artistimage for y in x.musicbrainzartworkgroup_set_filter]:
                logger.info(f"Admin:{x}アーティスト用画像が未適用です。確認してください")
            for y in x.musicbrainzartworkgroup_set_filter:
                if y.first_release_date in [None,""]:
                    logger.info(f"Admin:{x}/{y}初リリース日未登録です。確認してください")
                if len(y.musicbrainzartwork_set_filter) == 0:
                    logger.info(f"Admin:{x}/{y}アートワーク0件です。確認してください")
                if y.first_release_date not in [z.release_date for z in y.musicbrainzartwork_set_filter]:
                    logger.info(f"Admin:{x}/{y}初リリースアートワーク該当なしです。確認してください")
                for z in y.musicbrainzartwork_set_filter:
                    if z.release_date in [None,""]:
                        logger.info(f"Admin:{x}/{y}/{z}リリース日未登録です。確認してください")
                    if z.status == "Bootleg":
                        logger.info(f"Admin:{x}/{y}/{z}ブートレグです。確認してください")
                    if len(z.musicbrainztrack_set_filter) == 0:
                        logger.info(f"Admin:{x}/{y}/{z}トラック0件です。確認してください")

        text = " / ".join([x.name for x in queryset.filter(prod=True) ])
        logger.info(f"Admin:{text}チェック終了しました")
```

  * アーティストの出身国登録を行っているか?
  * アーティスト画像の登録を行っているか?
  * アートワークグループの初リリース日の登録を行っているか?
  * アートワークグループに対応したアートワークが1つ以上登録フラグが立っているか？
  * アートワークグループに対応した初リリース日のアートワークが登録されているか？
  * アートワークのリリース日が登録されているか？
  * アートワークがブートレグではないか？
  * アートワークの楽曲が1つ以上登録フラグが立っているか？

他にも
  * アートワーク画像がS3にアップロードされているか？
  * アートワーク画像の容量・画像サイズが基準を満たしているか？

などのチェックを行うことで登録ミスを防ぐようにしました

### 4.Python(+Docker)でのライブラリ管理

主に以下の事例から、ライブラリ管理を適切に行いたいと感じる場面がありました。
* あるPythonライブラリを標準インストールした際、依存関係でエラーが生じ、原因調査→一部依存ライブラリのダウングレード対応に時間を要した
* 一時期`requirements.txt`にVer指定を行っていなかったため、互換性がなくなる場面があった

Node.jsやRailsのパッケージマネージャは`package-lock.json`や`Gemfile.lock`といったようにlockファイルによるバージョン管理が一般的であり、かつnpmやbundleとDockerを比較的簡便に併用して使用することができます。
一方、Pythonにも同様なパッケージマネージャとして`pipenv`及び`Pipfile.lock`が存在するのですが、`pipenv`はライブラリ管理と仮想環境が密結合であり、Dockerと併用する際に一癖あります。

そのため今回は`pip`にて随時Ver情報を書き出すことでVer管理をするようにしました
`venv`の仮想環境にて`requirements-lock.txt`を随時書出・比較することで管理するようにしました

```sh:requirements-lock.txtの作成
timestamp=$(date +%s)
python3 -m venv .venv_temp_${timestamp}
source .venv_temp_${timestamp}/bin/activate
pip install -U pip wheel
pip install -r requirements.txt
pip freeze >| requirements-lock.txt
rm -rf .venv_temp_${timestamp}
```

```:requirements-lock.txt
attrs==19.3.0
・
・
・
zipp==1.0.0
zope.interface==4.7.1
```
