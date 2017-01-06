#css rayout basic

## user agent style (初期CSS)
  *はじめからついているcssはブラウザによって異なるので、同じ見え方をするために、cssのリセットを必要とする。
  -reset.css
    +ほぼ全部初期化
  -normalized.css
    +多少初期化

## developer tools
  - command + option + i

## footerの背景色を下までしたい
  - footer・body 背景色を同じ色とする

## eyecatch画像の配置の仕方
  ```
  eyecatch{
    background:url("url") no-repeat
    background-size:cover;
    background-position:50% 20% / center;
    height:100px / 100vh;
  }

## float 回り込みの解除方法 / claer:both;
  ```
  #right{
  float:left;
  width:10px;
  }
  #left{
  float:left;
  width:10px;
  }
  #footer{
  clear:both;
  }
  ```

## clearfix / overflow:hidden;
  ```
  .clear::after{
    content:'';
    display:block;
    clear:both;
  }
  ```
  ```
  .clear{
    overflow:hidden;
  }

## カラムに余白をつける
 -margin
 -padding
  *padding の計算が面倒臭い時 box-sizing:border-box;

## 3カラムの設定
```
.left{
  float:left;
  width:100px;
}
.center{
  float:left;
  width:300px;
}
.right{
  float:left;
  width:100px;
}
```
-clear fixも忘れずに

### :after/::after
-css2まで :after
-css3から ::after

## メニュー作成
###テキストを横並びにする
- display:inline-block

###inline-blockにより勝手に生じる各メニュー間の隙間を埋める方法
1. 親要素に font-size:0px;
2. 子要素に font-size:###px;

###リストの黒丸を消す
- list-style-type:none;

###リストの下線を消す
- text-decoration:none;

###縦横中央寄せ
- text-align:center;
- height:40px; line-height:40px;

###じわじわとロールオーバーで透明に
a:hover{
  opacity:0.5;
  transition:0.8s;
}

##positionプロパティで配置（画像の上に文字をのせる）
-html
```
<div class="product">
  <img src="">
  <span class="price">$100</span>
</div>
```
-css
```
.product{
  position:relative;
  display:inline-block;
}
.price{
  position:absolute;
  top:0; / top:-5px;
  right:0;
  padding:4px
}

```





