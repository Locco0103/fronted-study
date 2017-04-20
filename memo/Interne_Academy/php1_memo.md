# PHP1 memo
## PHPの概要
### PHP Hyper text Preprocessor
- 動的にHTMLデータを生成
- サーバ側で動作
- コンパイル(人が読めるものをコンピュータが読めるものに)が不要
- plug-inn が豊富 

## XAMPP
開発環境
X:クロスプラットフォーム
A:Apache
M:MySQL
P:PHP
P:Perl
- 通常apacheなどのWebサービス上で動かす。
1. oracle VM VirtualBox で仮装環境を作る
2. Xamppを開く
3. ファイル(htdocs)にphp1というファイルをいれる
4. ブラウザにて、http://localhost/php1 動作確認

## 基本文法
### HTML内にて
```
<?pho ~ ?>
```
- 大文字、小文字の区別なし
- 拡張子 .php

### 文字列の出力
```
<?pho
echo "<p>Hello</p>","Thank you";
print "Hello";
 ?>
```
- echo は複数の出力が可能
- タグも入れられる

### コメント
- 一行
//print　"hello";

- 複数行

## 基本的な構文

### 特殊文字
エスケープ処理
echo "<p>He said　¥"Hey¥" i didnt reply</p>"

スカラー: php一つ単位
リテラル: 値そのもの

### ヒアドキュメント
複数行の文字列をまとめて記述する。
<<< 終端識別子
  文字列
終端識別子

echo <<< _BODY_
<h1>###</h1>
<p>###</p>
_BODY_;

タブを入れてしまうとerrorとなる。

### ナウドック
ヒアドキュメントなし

### 変数
データを一時的に保管しておくもの
- 記号は_のみ使える
- 代入演算子
```
$変数名 = 値;
$A = 5;
```

デリミタ{}
<?php
$meal = "steak";
echo "he ate $meals";
echo "he ate {$meal}s";
?>

### 配列 Array
```
$配列名[数字のキー] = 値;
$A[0]= 3;
$B[1]= 4;
$C[2]= 5;
```
```
$配列名 = array[ , , ];
$B = [1,10,100];
$B[0]
```
```
<?php
$number[0] = 3;
$number[1] = 2;
$number[2] = $number[0] + $number[1];
echo "numberの値は、{$number[2]}です"
?>
```

### 連想配列
文字列のキーと値を一組のセットとして関連付けしてデータを保管しておくもの。
```
$配列名[文字列のキー]=値;
$sample["A"] = 80;
$sample["B"] = 100;
$sample["C"] = 120;
$sample = array("A"=>80,"A"=>100,"A"=>120);
```

```
<?php
$price = array("apple" => 80, "banana" => 100);
$num = array("apple" => 30, "banana" => 40);
$sum_price = $price["apple"] * $num["orange"];
echo "りんごの合計金額は、{$sum_price}です。"
?>
```

### 条件文
```
$a=10;
if($a<0){echo("a")}

```

### ループ文
- while
while(条件式){
  繰り返したい内容
}
```
$i = 3;
while($i >0){
  echo $i;
  $i--;
}
```
- for
for(初期値;条件式;更新式){
  繰り返したい内容
}
```
- foreach
foreach(配列as キー変数 =>値変数){
  処理
}
```
<?php
$fruits = array("banana","apple","peach");
foreach($fruits as $index => $value){
echo "$index : $balue <br>";
}
?>



















