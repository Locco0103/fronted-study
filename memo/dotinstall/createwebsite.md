createwebsite memo

css
{ margin: 0 auto;}  - 左右中央揃え

2カラム(可変幅)
  {
  float : left;
  width : 70%;
  }
  {
  float : right;
  width : 30%;
  }

2カラム(固定幅)
  overflow:hidden;　-　回り込み制御入っているタグに
  {
  float : left;
  width : 200px;
  }
  {
  float : right;
  width : 300px;
  }

  {
  margin-left : 300px;  - 左から300pxの位置に
  }

###{box-shadow: 0 0 3px rgba(0,0,0,0.5);}
  box-shadow: 縦　横　ぼかし rgba(red,green,blue,透明度);

menuの作り方
  -ul li タグで作成
  - #menu ul li{
    float:left;
    width:130px;
    background: #ccc;
    text-align: center;
    margin-right:10px;
    font-size:13px;
    padding:4px;
    border-radius: 6px;   角を丸く
    text-shadow:1px 1px 0 #ffffff;　影をつける
  }
  - リンクの下線を消す
  #menu ul li a{
    text-decoration:none;
    display:block;
  }


  -------------------------------
フォルダ内ワード検索
  - find in folder
    ダブル
