cssbasic memo

スタイル３つの方法:
  外部スタイルシート       - CSS
  ドキュメントレベルスタイルシート  - headタグ内
  インラインスタイル       - 直接一行

無効化：
  html内   - <!-- -->
  css内    - /* */

セレクタ：
  ユニバーサル  - *
  id      - #
  class   - .

セレクタ区切り方の違い：
  a,b     - aとbに
  a b     - aに所属するbに
  a > b   - aの直下にあるbにのみ
  a + b   - aの次にくるbに

属性セレクタ：
  aタグ 
    - a[title="###"]      - aのタイトルが###のタグ
    - a[class~="###"] - ###というテキストがあるタグ

擬似クラス：
  - 子要素 指定  - ul li:first-child
  - リンク   - a:link
        - a:visited
        - a:hovered
        - a:active

擬似要素：一部を指定するもの
  - :first-line - 一行目
  - :first-letter - 一文字目
  - :before {content:"###";}  - 前に###を挿入 
  - :after {content:"###";} - 後に###を挿入

セレクタ詳細度：複数のセレクタ時、どれが優先されるか？
  　高  - style=""
    - id
    - 属性/擬似クラス 
  　低  - 要素/擬似要素
  - !important  -最重要とできる

プロパティの値
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

menuの作成
  -display:flex;

padding順番
  - padding 上 下 左 右
----------------------------------------------
sublime shortcut
  - コメント : command + /
  - 行の移動 : command + control + カーソル
