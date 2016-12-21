# スマートフォン製作3 memo

##CSS3
###属性セレクタ
  - a[href$="pdf"]{background-color:red;}

###擬似クラスセレクタ
  - li:nth-child(2n/2n-1/odd/even){
  background-color:red;
  })

###ベンダープレフィックス
まだプラウザに実装されていないもの
  - h1{
  -moz-border-radius:20px;
  -webkit-border-radius:20px;
  border-radius:20px;
  }
  * IE -ms-
  * Fire Foc -moz
  * Google Chrome -webkit-
  * Safari -webkit-
  * Opera -o-

###カラムレイアウト（フレックスボックス）
ボックスの柔軟なレイアウト
  - <従来>
    子要素{float:left;}
  - <CSS3>
    親要素{display:flex;}

###Webフォント
@font-face{
  font-family:'example';
  src:url('font/example.woff')format('woff')
}
body{
  font-family:example, serif;
}

###複数の背景画像
- background-image:url(sample01.jpg), url(sample02.jpg);

###border-radius/text-shadow/box-shadow
  - border-radius:80px 100px 80px 100px;
  - text-shadow:3px 5px 5px #999; 水平方向 垂直方向 ぼかし半径 影の色
  - box-shadow:3px 5px 5px #999;

###transform/transition
  *  -moz-transform:rotate(-45deg);
    transform:rotate(-45deg);
  * h1{
  -moz-transition:background-color 1s linear;
  transition:background-color 1s linear;  1秒で徐々に
  }
  h1:hover{
    background-color:red;
  }

###グラデーション
  background: -webkit-linear-gradient(left, #FF0000, #0000ff);
  background: -moz-linear-gradient(left, #FF0000, #0000ff);
  background: linear-gradient(to right, #FF0000, #0000ff);

##body要素
 ### clear fix
 













