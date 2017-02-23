# responsive web design

## fontawesome の使い方
- 同じフォルダへfontawsome css font を
- html でリンクを
```
<link rel="stylesheet" href="css/font-awesome.min.css">
```

## スマホ対応の大きさにする方法(ビューポート)
```
<meta name="viewport" content="width=device-width,initial-scale=1.0">
```

## メディアクエリー
```
@media (min-width:570px){
  body{background:skyblue;}
}

@media (min-width:820px){
  body{background:lime;}
}
```

## youtube動画の埋め込み方法
1.youtubeの埋め込みコードをコピー
2.htmlの好きなところへペースト

### iframe の縦横比を合わせる方法
-html
```
<div class="frame-wrapper">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/MGwme_fmB30" frameborder="0" allowfullscreen></iframe>
</div>
```
-css
```
.how-to-use iframe{
  position:absolute;
  width:100%;
  height:100%;
  top:0;
  left:0;
}
.frame-wrapper{
  padding-bottom:56.25%;
  height:0;
  position:relative;
}
```