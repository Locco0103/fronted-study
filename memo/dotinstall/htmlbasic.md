#htmlbasic memo

cssリンク順番の覚え方：
	Love and Hate
		a:link
		a:visited
		a:hover
		a:active

<a href="###" target="_blank>：
	別ページとしてリンクを開く

<link rel="shortcut icon" href="画像.img">
	ファビコン(favorite icon)ブラウザのアドレスバーやタブに表示される小さいアイコン

<form action="phpやrubyの送信先" method="get / post">

inputでよく使われる属性(type="") 閉じタグいらない:
	text 		- アンケート等書き込むテキストボックス
		name		- 名前をつける
		size		- ボックスの大きさ
		maxlength	- 最大文字数
		value		- はじめから表示されるテキスト
		placeholder	- うっすらとはじめから表示されるテキスト
		required	- 入力必須項目
	submit		- 送信ボタン
	password	- 書き込みが見えなくするテキストボックス
	hidden		- 毎回打ち込むのが面倒な時、相手に送信される
	(選択肢のボタン)
	checkbox	- 複数の選択が可能
	radio		- 一つのみ選択可能
		label		- テキストを選択してもチェック可能(checked)
		label for="###" - idのテキストを選択してもチェック可能
	email		- メールのみ入力可能
	number		- 数字のみ入力可能
	date		- 日付のみ入力可能

閉じタグ必要:
	textarea 	- 記入欄
	button		- ボタン(送信のみではなくなんらかの処理)	


名称について：
	rel 	relation
	a 		anchor
	href 	hyper reference
	src 	source

	ol 		ordered list
	ul 		unordered list
	li 		list item

	dl 		definition list
	dt 		definition term
	dd 		definition discreption

	br 		line break
	hr 		horizontal rule

	thead	table head
	tbody	table body
	tr 		table row
	th		table header
	td 		table data