# my-webapp-foundation
小中規模Webアプリ製作用テンプレート

## 使い方
**事前にnode.js(もしくは io.js), npm, gulpのインストールが必要です。**

1. このリポジトリをダウンロード（画面右`Download ZIP`ボタン)
2. ダウンロードしたZIPを展開 （ここで展開されたフォルダを`プロジェクトフォルダ`とします。）
3. シェル（コマンドプロンプト）でプロジェクトフォルダに入って以下のコマンドを実行  
  - `npm i`
  - `gulp`
4. srcフォルダ内でファイル編集を行うと自動でビルドがかかります。  


## 機能
- srcフォルダ内のjade, styl, sass, coffeeファイルを自動的にビルドし  
publishフォルダ内に出力します。

- BrowserSyncにより、`http://localhost:3000/`にアクセスすることで  
編集内容をリアルタイムプレビューできます。（編集したら自動更新かかります。）

### jade, styl, coffeeなどの各ファイルについて
_mixinライブラリ_ や _レイアウトテンプレートファイル_ をビルドさせないために  
名前が "\_" から始まるファイルと、"\_"から始まるフォルダ内のファイルはビルドされません。  

### CoffeeScript, JavaScriptについて
- `JavaScript`・`CoffeeScript`で開発することが可能です。  
  どちらか片方、および両方の言語を使用することが出来ます。  
  たとえばJavaScriptで書かれたモジュールをCoffeeScriptからrequireすることも可能です。

- `src/coffee`, `src/js`をルートとしてファイル分割が可能です。  
  分割したファイルは`require関数`で読み込みます。

- `src/coffee`, `src/js`内のjadeファイルは無視されます。  
    (require関数を用いてクライアントサイドのテンプレートとして取り込むことが可能です。)

- `.coffee`, `.js`, `.cson`, `.json`, `.jade`をrequireすることが出来ます。

## ディレクトリ構成
`()`のフォルダは自動的に生成されます。  
`[]`のフォルダは必要であれば自分で作成してください。
```
Project
└ (publish)         -- 自動的に生成されて、リリースビルドが保存される。
│　└ js
│　└ css
│　└ img
│
└ src              -- 開発用ディレクトリ (jadeを保存 -> publish/以下に出力される)
│　└ coffee         -- CoffeeScript (publish/jsに出力される）
│　└ styl           -- Stylus (publish/cssに出力される）
│　└ img            -- 画像アセット(publish/imgに最適化されて保存される)
│　└ vendor_js      -- JavaScriptライブラリ用ディレクトリ (publish/jsにコピーされる)
│　└ [fonts]        -- WebFont用ディレクトリ (publish/fontsにコピーされる)
│　└ [css]          -- CSS (publish/cssにコピーされる)
│　└ [sass]         -- Sass (Sassを利用することが出来ます。 -> publish/css)
│　└ [js]           -- JavaScript (publish/jsに出力される)
│
└ gulp_config       -- Gulpのモジュール別設定ファイル
│
└ Gulpfile.coffee   -- Gulp設定ファイル
└ package.json      -- npm設定ファイル
└ bower.json        -- bower設定ファイル
└ README.md
```


## 今後
- [my-web-foundation](https://github.com/ucym/my-web-foundation)に取り込むかもしれない。
- TypeScriptに対応するかもしれない
- サンプルプロジェクトの用意

## 参考にしました
[frontainer/frontplate](https://github.com/frontainer/frontplate)
