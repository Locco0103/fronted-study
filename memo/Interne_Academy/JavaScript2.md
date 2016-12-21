# JavaScript2 memo

  ##イベント処理
    ###イベント
      - load : ページや画像の読み込みが完了
      - click　: クリックした時
      - mouseover : マウスが載っている時

    ###イベント処理方法
      1. 要素 window/document/getElementById('')/querySelector('')
      2. イベント load/click/mouseover
      3. どの処理に関連づけるのか function(){}

    ###イベント処理方法　例
    -方法1
      [HTML]
        <button onclick="show()">
      [JavaScript]
        <script>
          function show(){ window.alert('クリックされました')}
        </script>

    -方法2　インライン
      <button onclick="window.alert('クリックされました。')">ダイアログを表示</button>

    -方法3 オブジェクトのプロパティに割り当てる
      [HTML]
        <button id="btn">ダイアログを表示</button>
      [JavaScript]
        <script>
  ->        window.onload = function() {
            document.getElementById('btn').onclick = function() {
              window.alert('クリックされました。');
            }
          };
        </script>

        ※注意->が無いと'btn'を読み込まない。

    ###イベント処理方法 addEventListener()メソッド
      - document.getElementById('btn').addEventListener('click',function(){
         window.alert('クリックされました。');
        });
  
      -方法4 addEventListener()メソッド
      [html]
        <button id="btn">ダイアログを表示</button>
      [JavaScript]
        <script>
        window.addEventListener('load', function() {
          document.getElementById('btn').addEventListener('click', function() {
            window.alert('クリックされました。');
          });
          document.getElementById('btn').addEventListener('click', function() {
             window.alert('コピーされました。');
          });
        });
        </script>

    ###イベントの伝達方法
      -DOMツリー状に流れるイベント情報をどの時点で受け取るかを確定
        +キャプチャリング　上から下に(true)
        +バブリング 下から上に(false)

        <script>
          document.getElementsByTagName('div')[0].addEventListener('click',test,false);
          document.getElementsByTagName('p')[0].addEventListener('click',test2);
          function test(e){
              alert('divに割り当てたイベントが実行されました');
          }
          function test2(e){
              alert('pに割り当てたイベントが実行されました');
          }
         </script>

         ※ pに割り当てられたイベントが先に実行される

    ###practice2 「'続きを読む'をクリックで非表示であったテキストが表示される」
        -[css] .cont{display:none;}

        -[javascript]
        window.addEventListener('load',function(){  
          document.querySelector('#seminar+p a').addEventListener('click',function(e){
            e.preventDefault();
            document.querySelector('#seminar+p a').style.display='none';
            document.querySelector('#seminar~.cont')style.display='block';
          },false);
        },false);

        - querySelector() / ()内CSSセレクタをオブジェクトとして指定できるもの
        - + : 隣接セレクタ/ #seminar + p a
        - ~ : 関節セレクタ/ #seminar ~. cont
        - .style.display='none' 非表示 / .style.display='block' 表示
        - preventDefault() / タグが持つ性質をうちけす。リンクタグでページ先頭に戻る性質etc.

    ###未対応ブラウザへの対応
      - addEventListener / IE6以前の古いブラウザでは使えない
      - ユーザー定義関数
        fuction eventListener(element,event,listener){
          if(element.addEventListener){
            element.addEventListener(event,listener,false);
          }
          else{
            element.attachEvent('on'+event,listener);}
          }
        }

   ## 応用知識
    ### コーディング規則
      - .jsのファイル名は小文字で統一
      - utf-8
      - セミコロン省略しない
      - 文字列は""ではなく''
    ### 命名規則
      - 変数・関数の名前は先頭小文字のcamelCase
      - オブジェクトは先頭大文字のCamelCase
    ### script 記述位置
      - 動き重いもの body内 一番下
      - html5.js　などは一番上　型崩れしないために
    ### DOMアクセスを抑える
      - elem.innerHTML +='追加する要素';
        elem.innerHTML +='追加する要素';
        elem.innerHTML +='追加する要素';
      DOMのアクセス回数/innerHTMLへのアクセス数 3
      - var result ='初期値';
            result +='追加する要素';
            result +='追加する要素';
        elem.innerHTML = result;
      DOMのアクセス回数/innerHTMLへのアクセス数 1

  ## YUI 圧縮ツール
    - Javascript内コードでスペースや改行、タブなどを圧縮して軽くする。

  ## デバック方法 : バグを解消する方法
  -Firebug
  -Qunit



