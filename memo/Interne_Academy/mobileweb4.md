# スマートフォン製作4 memo

##レスポンシブ対応

  ###position
  -relative / 今の位置を基準とした位置
    position:relative;
    top:10px;
    left:50px;
  -absolute / 親ボックスの表示領域を基準とした位置
    position:absolute;
    top:

  ###JQuery Mobile
    ####メリット・デメリット
      -メリット
        +クロスブラウザ対策をほとんどしなくてよい
        +スマホ用デザイン、画面遷移を簡単に作成
      -デメリット
        +オリジナルのデザインを表現しにくい
        +低スペックのデバイス・環境では動きが遅い

    ####JQuery Mobileの導入
    ```
    <link rel="stylesheet" href="http://jquery.com/......"
    <script src=""
    <script src=""
    ```
    一つのhtmlが複数のページを持つ。
    二つのページを片方を表示・片方を非表示　→　スイッチ

    ####独自データ属性
    HTML5から追加
    -data-role="page"
    -data-role="header"
    -data-role="content"
    -data-role="footer"
    
    data-postition="fixed"

    ####カスタマイズ
      - themeroller
        色を変えてダウンロード

##Webサイトの高速化
  -リクエストするファイルの数を減らす
    *インライン　ニュースサイト・更新が多いサイトによい
    *外部ファイル 一般企業サイト
  -CSSスプライト:画像も一つのファイルに（一つのpngにアイコンを）
    *background-position:0 0;
  -どのファイルに何秒かかっているかの検証
    *検証 => Network?timeline?




