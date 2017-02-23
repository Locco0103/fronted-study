# Dotinstall 実践！ウェブサイトを作ろう memo (favicon / fontawesome / 背景画像)
## 02
### ショートカットキー[行の複製]
- shift + command + d

### ショートカットキー[行の削除]
- shift + command + backspace

### favicon
```
<link rel="icon" href="../images/###.ico">
```

## 03
### aタグの下線を消す
```
a {text-decoration:none;}
```

## 05
### 背景画像
```
header{
  background:url('../images/###.jpg');
  background-size:cover;
  background-position:center center;
}
```
1. url
2. 背景領域全体を覆う(cover)
3. 画像の中心とする。

### margin の相殺による余白
- 子要素に対して padding-top:10px

## 07
### fontawesome (アイコン)の導入
1. fontawesome ダウンロード
2. "fonts"フォルダ、"css"フォルダを作成中のフォルダへ
3. html linkタグで先ほどのCSSを読み込む
4. fontawesome サイト "Icons" にて使いたいアイコンを検索
5. コードをそのまま貼り付け