#JavaScript3 memo

##JQuery
  - JavaScriptの軽量ライブラリ

##JQuery 使用方法
  - CDN (Contents Delivery Network) / オンライン上でのみ使える
  - 同じローカルフォルダ内にjQueryのファイルをhtmlに読み込む

##JQuery 基本構文
  - CDN
  <script src="http://code.jquery.com/jquery-1.7.2.min.js"></script>
  
  ### $()関数
    - $(function(){});

    - $('#menu img.fade').fadeOut(3000);
    getElementByIdなどを使わずに指定できる。　
    '#menu img.fade'はオブジェクト

  ###基本的なメソッド（スタイル）
    - cssメソッド
      $(...).css(プロパティ名,値)
      + 単一
        $('a.new').css('background-color','Yellow')
      + 複数
        $('a.new').css({
          backgroundColor:'Yellow',
          color:'Red'
          });

    - addClassメソッド / クラス名を追加
      $(...).addClass(クラス名)

  ###基本的なメソッド(属性)
    - attrメソッド / 要素の属性を設定
      $(...).attr(属性,値)
      $('a.new').attr('target', '_blank');
        + a内のクラスnewをクリックした時、新しいタグで開く

  [head内JQuery]
      <script>
      $(function() {
        $('a.new').attr('target', '_blank');
      });
      </script>
  [body内JQUery]
      <script>
         $('a.new').attr('target', '_blank');
       </script>

  ###基本的なメソッド(操作)
    ####コンテンツの追加 html / text
    - htmlメソッド
      htmlタグとして
    - textメソッド
      textタグとして

    $(function(){
      $('#').html('<h1>###</h1>');
      $('#').text('<h1>###</h1>');
    });

    ####指定した要素を追加 before / after / prepend / append
      $(function() {
        $('#list').before('<p>バイオリン</p>');
        $('#list').after('<p>トランペット</p>');
        $('#list').prepend('<li>ハープ</li>');
        $('#list').append('<li>マリンバ</li>');
      });

      -before / after : 対象要素の前、後
      -prepend / append : 対象要素の子要素の前、後

  ###基本的なメソッド(エフェクト)(p.50)
    #### show/hideメソッド
      -showメソッド 非表示状態にある要素を表示
        $('...').show(ミリ秒.function{})
      -hideメソッド 表示状態にある要素を非表示
        $(function() {
          $('div').hide(5000, function() {
            location.href="https://www.internetacademy.jp";
          });
        });

    #### animateメソッド
      $(...).animate({
        プロパティ名:値,
        プロパティ名:値
      },時間)

  ###メソッドチェーン
    -複数のメソッドをドットで連結
    -$('div').sideUp(3000).fadeIn(3000).・・・;
        <script src="http://code.jquery.com/jquery-1.7.2.min.js"></script>
        <script>
        $(function() {
          $('div').slideUp(3000).fadeIn(3000).fadeOut(3000).slideDown(3000);
        });
        </script>

##イベント
  ###イベント処理
  1.どの要素で発生した window / document / getElementById('') / querySelector('')
  2.どのイベントを　load / click / mouseover
  3.どの処理に関連づけるのか function(){}

  ###処理方法
    $(function() {
      $('img').click(function() {
        $(this).fadeOut(3000);
      });
    });
      -$(this) : 上の$()内のもの

  ###イベントオブジェクト
    -イベントに関する様々な情報を管理し、イベントに関係する操作の手段を提供するオブジェクト
    -$(...).イベント名(function(e){
      イベントオブジェクト名.メソッド(...)
      });

##イベントオブジェクトのメソッドとプロパティ
  ###preventDefaultメソッド
    -本来持つ動作をキャンセルする
    -イベントオブジェクト.preventDefault()
      <head>
      <meta charset="UTF-8" />
      <script src="http://code.jquery.com/jquery-1.7.2.min.js"></script>
      <script>
      $(function() {
        $('form').submit(function(e) {
          if (!confirm('送信してもいいですか？')) {
            e.preventDefault();
          }
        });
      });
      </script>
      <title>jQuery</title>
      </head>
      <body>
      <form method="send.php" action="POST">
        氏名：
        <input type="text" name="name" />
        <input type="submit" value="送信" />
      </form>
      </body>

     -!confirm: OKとキャンセルの確認ボタン / キャンセルされたら〜をする

  ###clientX / clientYメソッド
  - X座標、Y座標を得る
      $(function() {
        $(document).click(function (e) {
          window.alert('X座標：' + e.clientX +
                       'Y座標：' + e.clientY);
        });
      });

  ###そのほかのイベント処理メソッド(p.58)
    ####oneメソッド - 一度だけ動作するもの
      $(function() {
        $('button').one('click', function(e) {
          window.alert('ボタンがクリックされました。');
        });
      });
    ####toggleメソッド - クリックのたびにパラメータに指定されたイベントリスナーを実行
      $(function() {
        $('button').toggle(
          function(e) {
            window.alert('ボタンが奇数回クリックされました。');
          },
          function(e) {
            window.alert('ボタンが偶数回クリックされました。');
          }
        );
      });
      -アコーディオンに使う
    ####hoverメソッド - 乗っている時だけファンクション実行
      $(function() {
        $('p').hover(
          function (e) {
            $(this).css('background-color', 'Yellow');
          },
          function (e) {
            $(this).css('background-color', '');
          }
        );
      });
  ###practice4(p.60) - サムネールをクリックするとメインの画像が変わる
    クリックしたターゲットをattrで呼び出す。









