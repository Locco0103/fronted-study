# php3 memo

## フォーム画面
### フォームの作成
HTMLで送信画面を作り、プログラム(PHPなど)でデータを受け取る。
```
<form action="" method = "">
</form>
```
#### action 属性
フォームに入力されたデータの送り先を指定。
```
<form action = "test.php">
```
送信先にメールアドレスをいれてしまうと、迷惑メールなどが増える。

#### method 属性
GETもしくはPOSTの送信形式を指定
- GET : 検索ボックスなど
- POST : データ量の多いもの

#### enctype 属性
MIMEタイプ（データの種類のこと。インターネット上でデータを正しくやりとりするために必要）を指定する。
##### application/x-www-form-urlencoded
初期設定。入力したデータをURLエンコードして送る。
##### text/plain
テキストデータとして送信
送信先がメールアドレスの場合
##### multipart/form-data
画像などのファイルを送信する場合

### input
さまざまな部品を作る空要素のタグ。
```<input type="text" name="name">```
- name
部品の名前を設定する。例えばPHPプログラムではname属性に指定した、文字列をキーワードとして取り出すことができる。
**type と name は必須**
- value
プログラムに送信する具体的な内容を設定
※テキストボックスの場合あらかじめ画面にでる文字

### ラジオボタン
単一選択ボタン
```
<input type="radio" name="gender" value="男性">
<input type="radio" name="gender" value="女性">
```
### チェックボックス
複数選択ボタン
```
<input type="checkbox" name="gender" value="男性">
<input type="checkbox" name="gender" value="女性">
```
### 送信ボタン
```
<input type="submit" name="submit2" value="送信する">
```
### 隠しフォーム
画面上には何も表示されずに、Webサーバーにデータを送ることができる。
```
<input type="hidden" name="" value="">
```
### テキストエリア
複数行タイプのテキスト入力枠
```
<textarea name="comment"></textarea>
```
### セレクトボックス
プルダウン式のメニューになる。都道府県のように選択肢が多い場合
```
<select namel="prefecture">
  <option value="1">北海道</option>
  <option value="2">青森県</option>
</select>
```

## フォーム処理
### フォームデータの受け取り
$_GET / $_POST に格納される

```
<input type="text" name="tel">
```
入力された文字は$_GET 内 key[tel]として格納される。写真参照


#### HTML FILE
```
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>フォームPHP3</title>
</head>
<body>
<form action="sample_form.php" method="get">
   <p>
       ■お名前<br>
     <input type="text" name="name" size="40">
   </p>
   <p>
       ■コメント<br>
     <textarea name="comment" col="40" row="6"></textarea>
   </p>
         <input type="submit" name="sub" value="送信する">
</form>
</body>
</html>
```
#### PHP FILE
```
<?php
$name = $_GET["name"];
$comment = $_GET["comment"];

echo <<< _FORM_
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>確認フォームPHP3</title>
</head>
<body>
   <p>
       ■お名前<br>
    $name
   </p>
   <p>
       ■コメント<br>
       $comment
   </p>
</body>
</html>
_FORM_;
?>
```

### 文字コードの処理
Shift-JIS / UTF-8

#### 文字コードを検出
mb_detect_encoding
```
$str ="インターネットアカデミー"
$str = mb_detect_encoding($str,"shift_JIS");
echo $str;
```
#### 文字コードを変換
mb_convert_encoding

#### 改行コード
windows CR+LF ¥r¥n
Mac(old ver.) CR ¥r
Mac,Unix LF ¥n

#### str_replace 関数　置換
指定した文字列の中からある文字列を別の文字に置き換える。

### HTMLの特殊文字の処理
危険とされる特殊文字 < > " & '
HTMLエンティティに変換して特殊文字を無効化する。
セキリュティも高まる。

## お問い合わせページ作成 php_b/php3/form/form.php
### 事前
- 文字コード utf-8 メールは件名と本文 JISコード
- 確認画面　すぐ送信完了では危ない

### UTF-8 / UTF-8N
- UTF-8 BOM がつく
- UTF-8N BOM がつかない　最近は不要
BOM: バイトオーダーマーク

#### preg_match メール入力確認













