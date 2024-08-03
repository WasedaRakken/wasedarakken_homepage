# このホームページについて
## 必要技術
* ホームページコーディング言語(html, css, javascript)
* javascriptフレームワーク:Vue.js
* Vueのプラグイン：ElementPlus

## 開発環境
* Node.jsのインストール
* npm
ルートディレクトリ(src, publicフォルダ等の上)でサーバーを立ち上げる。
```
npm run serve
```
以下の操作で公開する前に必ず、自分のサーバ上(8080ポート)で確認する。

ビルド(GithubPagesで公開するなら、docsフォルダに吐き出させた方がいいのでdocsフォルダに吐き出せるようにvue.config.jsを編集)
```
npm run build
```
これで、docsフォルダ内にcss, html, javascriptが吐き出されるはず。
あとは、docsフォルダをこのリポジトリにアップロードすれば自動でデプロイされて公開されます。

* Vue周りの環境
  * vueCLI
  * router


## 構成
* srcフォルダ内で以下の構造をとる。
<pre>
src
├─assets
|  img00.jpg            使用している画像素材
|   ..etc
│  └─fonts/フォントファイル用フォルダ(NotoSansのttfファイル)
├─components
|   PastEventInfo.vue  わせだ寄席ページの過去のわせだ寄席に関する
|                    情報をコンポーネント化した部品
├─plugins
|   element.js
├─router
|   index.js
|
└─views
    AboutView.vue      活動紹介
    ContactView.vue    出演依頼
    EventView.vue      わせだ寄席
    FreshmenView.vue   新規入会     JoinusView.vueとかの名前が良かったかも、、
    HomeView.vue       Home
    Thisyear.vue       今年のわせだ寄席ページ 
App.vue                viewsフォルダのルートファイル。主にheader, footer, router遷移
element-variables.scss
main.js
style.scss
</pre>

* その上の構造は以下の通り。環境を構築すればこの辺の構造は勝手にインストールされます。
* なので、基本コーディングはsrcフォルダの中身、特にVueファイルを書くことだけです。
<pre>
├─dist
├─docs                GithubPagesはdocsフォルダを作って吐き出させると公開できる。
|  ├─css              最終的にこのdocsフォルダを作ることが目的。これをアップロードして
|  ├─fonts            デプロイすれば公開されます。
|  ├─img
|  └─js
├─node_modules
├─public
└─src
.gitignore
babel.config.js
jsconfig.json
package.json
package-lock.json
README.md
vue.config.js          いじるとしたらこのconfigファイル
</pre>

* 各ファイルの中身は、このドライブから確認できます。（このGithubリポジトリは公開されているので、念のため別に保存してます。ラッケンのGoogleアカウントでログインできます。）

## 今後の計画(未実装、バグ等)
* Google Analysisを入れてみる。
* →認証がめんどそうなのでまた今度
* スライドする時間間隔遅くていい
* 関連リンクとして、落穂会
* 開発はリポジトリをクローンしてもらえばできるか。→それようのプライベートリポジトリを作成。
* ~~RouterでViewを移した時に一番上から表示されない~~
* ~~twitter入れ込む~~
* Instagram連携はまた今度→APIが必要
* 早稲田大学落語研究会のロゴを入れ込む、どっかに
* ~~ヘッダーの幅が明らかにデカくてズレてる~~→blocksizeで解決
* 慰問の文言変えとく
* Google検索かけた時のアイコンが未表示


### 引継ぎ
->とりあえず、Docker使わないVerをやってみるために、Assetsフォルダをどっかにアップロードして、Macで立ち上げられるか確認する。
* クローン用のリポジトリの名前をdev_for_rakkenhpとかに変える
* 過去のHPを一応公開しておく？→少なくともリポジトリを作っておく
* Dockerでイメージを作ろう。
* 色々説明が入ったリポジトリ(クローン用でいいか)と、前のHPを公開できるリポジトリ、あとはHP更新用の情報を誰かに引き継ぐ




## 開発者向け
以下はここでは詳しく解説しないので、なければインストールしてください。
* Visual Study Code
* Github

### ①PCに環境を構築して開発する
* 自分のPCで開発するディレクトリを決める。（Users/wasedarakken/Documents/hp_dev00など）
* そこのディレクトリまで移動し、Node.jsをインストール

参考： [Windowsでのインストール](https://qiita.com/C_HERO/items/318fe65871f8e53e8c80)
> ⚠️ **注意** 
> - Windowsでは、Node.jsのインストーラをインストールすればnpmもついてくる。
> - npmとはNode.jsの開発用コマンドみたいなものです。

* npmが正しく使えるか確認します。コマンドラインで
```
npm -v
```
のようにしてバージョンを確認。バージョンが無事確認できたら
* らっけんのHPソースコードが保管してあるgithubリポジトリを、先ほど作成した自分の開発ディレクトリにクローンします。
* 写真などのデータが重すぎてGithubにアップロードできていないので、別途ダウンロードします。

 大変
* クローンしたディレクトリ(dev_for_rakkenhp)に移動して、依存関係(ファイルの階層構造)を覚えさせます。
```
npm install
```
* 開発環境が整ったか確認します。
```
npm  run serve
```
* これで上手くいけば、(http://localhost:8080) などでアクセスできるようになります。
> ⚠️ **注意** 
> - 一回でうまくいくことはほぼないので、対話型AIにエラーを喰わせるなどして何とか起動できるように頑張ろう。
