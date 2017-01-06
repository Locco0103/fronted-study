#CSS3basic memo

##canIuse.com
  -緑：ブラウザ対応
  -赤：ブラウザ対応していない
  -縁取り：現在のブラウザ

##値 px/em/%/rem
  -em   : emphasize       :親要素を基準とした値
  -rem  : root emphasize  :ドキュメント(html)を基準とした値

##色 rgba/hsla
  -rgba( , , , )
    + red
    + green
    + blue
    + alpha (0-1)
  -hsl( , , , , ) / hsla( , , , , )　:　直感的に明るくしたり暗くしたりしやすい！
    + Hue         :色相   :0-360    / 色の360度回転した中で
    + Saturations :彩度   :0-100%   / 0でモノクロ
    + Lightness   :輝度   :0-100%   / 0で黒 100で白
    + alpha       :透明度  :0-1

##透明度 opacity
*フォントや背景色でないものに透明度を加えたい時
  -opacity:0-1;

##属性セレクタ
  - a[href]
  - a[href="url"]
  - a[href~="url"]

  - a[href^="http"] httpからはじまる
  - a[href$=".com"] .comで終わる
  - a[href*=".co.jp"] .co.jpを含む

##擬似クラス
  ### nth-child
  - :first-child
  - :last-child

  - :nth-child(2)
  - :nth-child(odd)
  - :nth-child(even)
  - :nth-child(3n+1)    :1,4,7,...
  - :nth-last-child(2)  :最後から数えて
  - :only-child         :子要素が一つだけのもの

  ### first-of-type / last-of-type　/nth-of-type
    *途中に他の要素が入っていても大丈夫

  ### not /empty /enabled /disabled /checked
  - :not(.###)  :.###でないもの
  - :empty      :空タグ
  - :enabled    :テキストボックスなどが有効な時
  - :disabled   :有効でない時
  - :checked    :checkボックスでcheckされた時

## 角丸 border-radius
  - border-radius:10px;     :半円10px
  - border-radius:30px / 10px   :楕円形　幅30px高さ10px
  - border-bottom-right-radius  :右下のみの設定
  - border-radius:50%           :正円のつくりかた

##背景画像の指定 background-size / background-position
  +background-size
    -contain /縦横比保持, 画像全体が必ず見える
    -cover   /縦横比保持, 領域全体を必ず覆う
    -px指定 10px 10px
    -%指定 50% auto
  +background-position
    -center / 50% 50%

## 線形グラデーション linear-gradient()
  * background-image:linear-gradient();
    - linear-gradient(lime, green);
    - linear-gradient(to top left,lime, green);  :左上に向かって
    - linear-gradient(60deg,lime,green);         :上から60度傾けて
    - linear-gradient(60deg,white,lime,green);   :3色
    - linear-gradient(white 40%,lime 40%,green); :3色割合
    - repeating-linear-gradient(white,lime 50px);:繰り返し

## 円形グラデーション radial-gradient()
  * background-image:radial-gradient();
    - radial-gradient(white,lime);
    - radial-gradient(at 200px 180px,white,lime);                       :at 出発点
    - radial-gradient(ellipse 100px 120px at 200px 180px,white,lime);   :楕円形の範囲内で(ellipse省略可)
    - radial-gradient(circle 30px at 30px 40px,white,lime);             :円形の範囲内で(circle省略可)
    - radial-gradient(farthest-side at 30px 40px,white,lime);           :出発点から最も遠い辺に向かって
    - repeating-radial-gradient(white,lime 30px);                       :繰り返し

## box-shadow / text-shadow
  ### box-shadow
    - box-shadow: 10px 20px 30px 10px rgb();    : 横ずらし　縦ずらし　ぼかし　大きさ
    - box-shadow: 10px 20px 30px 10px rgb(), 10px 10px 20px 10px rgb() inset;    : 影２つと内側にいれる方法

  ### text-shadow
    * insetつけられない
    * 4番目の大きさの指定はできない。

## flexbox　テキスト縦横中央揃え
  ```
  display:flex;
  justify-content:center;
  align-items:center;
  ```

## 変形 transform
+transform
  - translate(10px,20px) / translateX :移動
  - scale(0.5,1.5)                    :大きさ
  - skew(10deg,20deg)                 :傾斜
  - rotate(30deg)                     :回転
+transform-origin
  - transform-origin: 0 0             :中心点

## ベンダープレフィックス
  *ブラウザが実験的に対応しているもの
    -firefox                : -moz-
    -opera                  : -o-
    -Google Chrome / Safari : -webkit-
    -Internet Explore       : -ms-

## transition プロパティ
  -transition-property        : どのプロパティを変化させるか    : all / width / color /...
  -transition-duration        : 変化にかかる時間             : 2000ms / 2s
  -transition-timing-function : 変化の仕方                  : ease / ease-in / ease-out / ease-in-out / linear
  -transition-delay           : 変化が始まるまでの時間         : 200ms / 2s
  [timing-functionの違いが見易い](http://weboook.blog22.fc2.com/blog-entry-313.html)

## animation プロパティ
  -animation-name             :名前
  -animation-duration         :
  -animation-timing-function  :
  -animation-delay            :
  -animation-iteration-count  :何回おこなうか    :数値 / infinite
  -animation-direction        :方向            :alternate(交互に)

  -@keyframes 名前{
  0%{}
  50%{}
  70%{}
  }

## box-sizing
  *padding/borderをいれる時にwidth/heightを計算し直していれるの大変！
    -> box-sizing:border-box;


