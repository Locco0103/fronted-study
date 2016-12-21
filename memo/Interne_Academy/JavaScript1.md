# JavaScript1 memo

##オブジェクト指向
  1. オブジェクトの指定
  2. プロパティ(オブジェクトの状態や特性) / メソッド(オブジェクトを操作する命令)
    -オブジェクト.プロパティ;
    -オブジェクト.メソッド(パラメータ１,パラメータ2.・・・);

##BOMとDOM
  - Browser Object Model
  - Document Object Model

##BOM

###windowオブジェクト
  - alertメソッド
    指定された文字列をダイアログボックスに表示
    <script type="text/javascript"
      window.alert('こんにちは');
    </script>
  - confirmメソッド
    [OK キャンセル]の二択のダイアログボックスの表示
  - setIntervalメソッド
      window.setInterval(function(){###},1000);
      + ###:実行する内容
      + 1000:1秒
  * 例1
      window.setInterval(function() {
        document.getElementById('msg').innerHTML = (new Date()).toLocaleString();
      }, 1000);
  * 例2
      function aaa(){
        document.getElementById('msg').innerHTML = (new Date()).toLocaleString();
      }
      window.setInterval(aaa,1000);

###formオブジェクト
  +HTML
    <form name="フォーム名">
      <input type="◯◯◯"　name="要素名">
      <input type="◯◯◯"　name="要素名">
    </form>
  +JavaScript 3つの書き方
    1.document.フォーム名.要素名
    2.document.forms[フォーム名].elements[要素名]
    3.document.[フォーム名][要素名]

  -valueプロパティ
    document.form オブジェクト.value
    ```
    function show(){
    window.alert(document.fm.txtMemo.value);
    //window.alert(document.forms['fm'].elements['txtMemo'].value);
    //window.alert(document['fm']['txtMemo'].value);
    return false;
    ```
    ```
    <form name="fm" onsubmit="return show()">
    <label>メモ：<input type="text" name="txtMemo"></label>
    <input type="submit" value="送信" />
    </form>
    ```
    
  -checkedプロパティ
    <script type="text/javascript">
      function show(){
        var items = [];
        var os = document.fm.os;
        for (var i = 0; i < os.length; i++) {
          if (os[i].checked) { items.push(os[i].value); }
        }
        window.alert(items);
        return false;
      }
    </script>

    <form name="fm" onsubmit="return show()">
      使用OSは？：
      <label><input type="checkbox" name="os" value="win" />Windows</label>
      <label><input type="checkbox" name="os" value="mac" />Mac</label>
      <label><input type="checkbox" name="os" value="lin" />Linux</label>
      <input type="submit" value="送信" />
    </form>

###locationオブジェクト
  - location.href='https://www.'
    履歴残す
  - location.replace('https://www.')
    ブラウザに履歴を残さない

##historyオブジェクト
  - <a href="JavaScript:history.back()">戻る</a>
  - <a href="JavaScript:history.forward()">進む</a>

##navigatorオブジェクト
  - ブラウザによって異なる動作をできる
  - var ver = navigator.userAgent;
    if(ver.indexOf('MSIE9')>=0){
      window.alert('IE9です。
    ')
    }
## indexOfメソッド
  -指定された文字列が現在の文字列に登場する位置を0以上の値で返します。(含まれない場合は-1を返します。)

## p.11あるブラウザの時にはパソコンサイト　あるブラウザの時にはモバイルサイトを開く
  - ブラウザの判別/navigatorオブジェクト
    if((navigator.userAgent.indexOf('iPhone') > 0 
      && navigator.userAgent.indexOf('iPad') == -1) 
      || navigator.userAgent.indexOf('iPod') > 0 
      || navigator.userAgent.indexOf('Android') > 0)
      )
    + &&:かつ
    + ||:または
    + iPhoneかつiPadでない　または　iPod　または　Android　である時

    <script type="text/javascript">
      if ((navigator.userAgent.indexOf('iPhone') > 0 && navigator.userAgent.indexOf('iPad') == -1) || navigator.userAgent.indexOf('iPod') > 0 || navigator.userAgent.indexOf('Android') > 0) {
        if(confirm('スマートフォンサイトに移動しますか')){
          location.href = 'smartphone/index.html';
        }
      }
    </script>
  - さらに'スマートフォンサイトに移動しますか'でokをしたら'smartphone/index.html'へとぶ。

  ##DOM
    ###nodeの取得
      - ダイレクトアクセス
        +getElementById(id) : id属性
        +getElementsByTagName(name) : tagの名前
        +getElementsByClassName(class)  : Class属性
      - ノードウォーキング / 現在指定している要素から　p.14
      - ノードの戻り値

    ###ノードの追加/置換/削除
      - createElementメソッド
        + var li = document.createElement('li')
          * createElement:（）内に記述したタグを生成することができる
          * 生成したliタグはliという変数に代入している
        + var txt = document.createTextNode('特徴')
          * 文字列の生成を行いたい時、createTextNode

      - appendChildメソッド/ノードの追加
      [HTML]
        <ul id="list">
        <li><a href="http://www.internetacademy.jp/">ホーム</a></li>
        </ul>
      [javaScript]
        <script type="text/javascript">
        var ul = document.getElementById('list');
        var li = document.createElement('li');
        var a = document.createElement('a');
        a.href = 'http://www.internetacademy.jp/feature/';
        var txt = document.createTextNode('特長');
        a.appendChild(txt);
        li.appendChild(a);
        ul.appendChild(li);
        </script>

        ここでは同じことをJavaScriptで面倒くさくやっているが、後々便利になる。

      -replaceChildメソッド/ノードの置換
      -removeChildメソッド/ノードの削除

      ###classNameプロパティ
        <div id="msg">classNameプロパティ</div>
        <script type="text/javascript">
        var msg = document.getElementById('msg');
        msg.className = 'sky';
        </script>

    ## Selectors API
      - CSSの記述文法を利用
      - var item = document.querySelector('CSSセレクタ')
        var items = document.querySelectorAll('#l2 li')






































