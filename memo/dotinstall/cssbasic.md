#cssbasic memo

##スタイル３つの方法:
  外部スタイルシート       - CSS
  ドキュメントレベルスタイルシート  - headタグ内
  インラインスタイル       - 直接一行

##無効化
  html内   - <!-- -->
  css内    - /* */

##セレクタ
  ユニバーサル  - *
  id      - #
  class   - .

##セレクタ区切り方の違い
  a,b     - aとbに
  a b     - aに所属するbに
  a > b   - aの直下にあるbにのみ
  a + b   - aの次にくるbに

##属性セレクタ：
  aタグ 
  <a href="http://###" title="###" class="###"></a>
    - a[href="http://###"] / aのリンク先がhttp://###のタグ 
    - a[title="###"]  / aのタイトルが###のタグ
    - a[class~="###"] / ###というテキストがあるタグ

##擬似クラス
  - 子要素 指定  - ul li:first-child
  - リンク   - a:link
        - a:visited
        - a:hovered
        - a:active

##擬似要素：一部を指定するもの
  - :first-line - 一行目
  - :first-letter - 一文字目
  - :before {content:"###";}  - 前に###を挿入 
  - :after {content:"###";} - 後に###を挿入

##セレクタ詳細度：複数のセレクタ時、どれが優先されるか？
  　高   - style=""
        - id
        - 属性/擬似クラス 
  　低   - 要素/擬似要素
  - !important  -最重要とできる

##プロパティの値
  - フォント
    - px
    - em    -親要素からの割合
    - %     -親要素からのパーセント
  - 色
    - 名前    - blue
    - RGB   - #00f
          - #0000ff
          - rgb(0,0,255)
          - rgb(0%,0%,100%)

##menuの作成
  -display:flex;

##padding順番
  - padding all
            top/bottom right/left
            top right/left bottom
            top right bottom left

##widthとheight
  - width %表示 親要素に対して
  - height %表示 親要素に対してだが、親要素全てにheight属性をつける必要がある。

##border について
  +border-color
  +border-width
  +border-style: solid/ dotted /dashed/ double / inset / outeset
  -border: orange 3px dotted なども可

  +border-top / border-bottom / ..

##body余白の初期設定
 body {margin:0;} / ボディのマージンを消す

##margin の相殺
  二つのbox間のmarginは大きい方のmarginとなる

##text
  - color:orange;
  - font-size:14px;
  - font-family:Arial, Helvetica;
  - font-weight:bold / none;
  - text-align: right/center/left ;
  - text-decoration: underline/line-through/none

##list
  - list-style-type: disc/circle/square/decimal/lower-alpha
  - list-style-img: url('');
  - list-style-position: inside/outside
  - list-style

##cursor
  - cursor:help/move/pointer/url('###''),auto 

##background
  - background-color: 
  - background-image: url('')
  - background-repeat: no-repeat/repeat-x
  - background-position: 10px 10px/ top center
  - background-attachment: scroll/fixed

##display
  - block (h1 / p / div)
    +widthで幅指定
    +勝手に改行
  - inline(span / a)
    +widthで幅指定　不可
    +改行されない
  - inline-block
    +inlineだがwidthで幅指定
  - list-item
  - none

  - table
  - table-cell
  - table-row
    +使い方
      .container{
        display:table;
      }
      .row{
        display:table-row;
      }
      .box{
        display:table-cell;
        width:100px;
      }
      .gray{background:gray;}
      .pink{background:pink;}
      .orange{background:orange;}
      .yellow{background:yellow;}

      <div class="container">
        <div class="row">
          <div class="box gray">gray gray gray gray gray gray</div>
          <div class="box pink">pink pink pink pink pink pink</div>
        </div>
        <div class="row">
          <div class="box orange">orange orange</div>
          <div class="box yellow">yellow yellow yellow yellow yellow yellow yellow </div>
        </div> 
      </div>

##position
  -static / はじめの位置
  -relative / 親要素からの相対距離
  -fixed / スクロールに関わらず固定
  -absolute /絶対位置

##z-index
  - static以外のpositionに有効

##overflow (はみだしているテキストに対して)
  - visible /そのままはみだす
  - hidden  /はみだしたものを隠す
  - scroll  /はみだしたものをスクロールでみる

##line-height
  - ボックスの大きさ
  - font-sizeに対しての割合で大きさを指定したい時
    font-size:18px;
    line-height:1.5;

##vertical-align
  - baseline / top / bottom / middle

##float
  - left / right

##clear floatによる重なりを解除
  - left / right / both
  - block要素にのみ

----------------------------------------------
sublime shortcut
  - コメント : command + /
  - 行の移動 : command + control + カーソル





























