# php2 memo
## FTPソフトの役割 

permission
ユーザに対するアクセス権
- 所有者権限
    - オーナー
    - グループ
- 実行権限


# 関数
戻り値を返す
パラメータ = 引数

### rand関数
```
 $b = rand() ;
 echo $b . "<br>";
 $c = rand(1,6) ;
 echo $c;
 ```

# ビルトイン関数
***もともとPHPに用意されている関数***

### ファイルを開く
- fopen関数
```
$file_handle = fopen($filename,"r+");
```
fopenに追記するオプションとなるモード p.22
r+ : 読み書き
a+ :追記で読み書き

```
$fh = "animals.txt";
$file_handle = fopen($fh , "a+");
fwrite($file_handle , "Wolf\n");
fclose($file_handle);
echo "Wolfを追加しました。";
```

### ファイルの編集
- fgets関数 / ファイルハンドル内の文字列を一行取得する。 
- fread関数 / ファイルハンドル内の文字列を取得する。
- fwrite関数 / ファイルハンドル内に書き込みを行う。

### ファイルを閉じる
- fclose関数 

### ファイルハンドルをロックできる
- flock関数

## ディレクトリ管理をするビルトイン関数

### ファイル操作
- chmod("ファイル名",モード) /change mode

### ファイル名の変更
- rename("ファイル名1","ファイル名2")

## プログラム制御
### PHPスクリプトの実行終了
- exit(ステータス)
```
<?php
$a = 123;
if($a == 123){
 echo "exitしました";
 exit();
}else{
 echo "exitしませんでした";
}
echo "最後の処理";
```
### exit関数のエイリアス（分身）
- die(ステータス)

## 文字列操作
### 文字列を指定したパターンで分割し、配列を返す
- explode('パターン',文字列)
```
<?php
$data = "1,apple,150,25";
$id = explode(',',$data);
echo <<< END
ID：$id[0]
名前：$id[1]
料金：$id[2]
個数：$id[3]
END;
```
### 配列から一つの長い文字列を作成（explodeの逆）
-　implode関数

### 文字列を指定したフォーマットに変更します。
- sprintf関数

## 配列制御 
- array_pop関数 :　配列の末尾を削除
- array_push関数 :　配列の末尾を追加
- array_shift関数 :　配列の先頭を削除
- array_unshift関数 :　配列の先頭を追加
- sort関数 : 指定したリストを照準に並び替え
- each関数 : 指定した連想配列のキーと値を取り出す

## 時間取得
- time関数 : 現在のUNIXタイムスタンプ 1970年1月1日00:00から
- mktime関数 : 指定した日付のタイムスタンプ $time = mktime(時,分,秒,月,日,年);
- date関数 : 書式に応じた日時を取得する

# ユーザー定義関数
- 自分で作成する関数
- 一連の流れをまとめて待機させておくもの (plugin的な？)
function の後、関数名
```
function tax($price){
  $tax_price = $price * 1.08;
  return $tax_price;
}
echo tax(200);
```
- パラメータを使用しない場合
    - パラメータ = 変数 
```
call();
function call(){
  echo "Hello world";
}
```
ユーザー定義関数 callを呼び出しなさい。

- パラメータを使用する場合
```
calc(1,2);
function calc($a,$b){
  $ans = $a + $b ;
  echo "$ans\n"
}
```
## 戻り値　***（上と比べてどういう時に便利になるのであろうか？）***
実行結果を返し、関数を終了させる。
```
$ans = $calc(1,2);
echo $ans;

function $calc($a,$b){
  $c = $a + $b;
  return $c;
}
```
- ユーザー定義関数 calc

## 局所化
- 変数を関数などのブロック内だけで使用できるようにすること。
```
function test(){
  # 局所化させる
  $data = 5;
    echo $data;
}
test();
echo $data;
```
局所化された変数：ローカル変数　名前の重複を抑えられる。
```
function test(){
  # 局所化させる
  global $data;
  $data = 5;
    echo $data;
}
test();
echo $data;
```
グローバル変数へ

# 環境変数
サーバやブラウザなどの基本的な設定が保存されている特別な変数。
- getenv(キー名)
```
$agent = getenv("HTTP_USER_AGENT");
if(strpos($agent,"iPhone")==true || strpos($agent,"Android")==true){
echo "スマホ用のサイトです";
}else{
echo "PC用のサイトです";
}
```
- HTTP_USER_AGENT ブラウザ情報を取得できる


























