# Lispの基礎
Lispとは List Processorの略であり、リストとよばれる可変長のデータ列を用いてデータを処理する動的言語となっている。<br>
Lispの集合には、Common Lisp、 Scheme、 Clojure、 Racket等があるが、一般的にLispと呼ぶ場合はCommon Lispのことを指す。<br>
開発者のJohn McCarthyは「人工知能：Artificial Intelligence」という言葉の提唱者であり、人工知能プログラムに多く使われる。<br>

|年|イベント|
|:---:|:---|
|1958|John McCarthyがLispを考案|
|1984|ANSIにより標準化されたCommon Lispが登場|
|1998|Yahoo!Store(Lispで書かれている)がショッピングモールサービスを提供|
|2007|関数型プログラミング言語Clojureが登場|


参考URL：
[Lispまとめ1](https://qiita.com/HaruoWakakusa/items/64f1b9a3f15ce85f0d0c) <br>
[Lispまとめ2](https://qiita.com/minekai374/items/f146009b403ed9395fe0) <br>
[Lispまとめ3](https://blog.codecamp.jp/lisp) <br>
[Lispまとめ4](http://bach.istc.kobe-u.ac.jp/lect/ProLang/org/lisp.html) <br>
[Lispまとめ5](http://www.shido.info/misc/index.php) <br>


## 項目 [Contents]

1. 理論 (#ID_1)

2. [install] (#ID_2)


<a id="ID_1"></a>
***

## 1. アトム
リストではないデータのことを指し、文字列や数値、シンボルのことである。ここで、シンボルとは「変数を格納する場所の名前」である。プログラム上では```'```を付ける必要がある。


```lisp

; アトムの例

* 42

* "atom"

* 'symbol

```

特殊なシンボルの例

```lisp

; パッケージ名や関数のキーワード引数を表現するのに使われる
* :keyword

; 空リスト or 偽値
* nil

; 真値
* t
```

***

## 2. リスト
リストとは、括弧```()```で囲まれた要素を連ねた形式で表される。<br>
関数呼び出しと差別するために```'```をつける。<br>
必ず1つ以上の空白文字で区切る。<br>

```lisp
; 数値のリスト
* '(1 2 3)

; シンボルのリスト
* '(a b c)

; シンボルと文字列のリスト
* '(format t "hello~%")

; 関数呼び出し
* (format t "hello~%")

```

### リストの連結

``` lisp
* (append '(a b) '(c d))
```

### リストを使ったwhileループ

``` lisp
* (while listが空かどうかのテスト
     処理....
     listに自分自身のcdrをセット)
```

増加カウンタの例

``` lisp
(while (<= row-number number-of-rows)
  (setq total (+ total row-number))
  ; インクリメント
  (setq row-number (1+ row-number)))
```


***


## 3. 関数定義

関数定義は```defun```を使い、引数をとる関数を定義するときは```lambda```の後に引数リストを置く。

``` lisp
* (defun hello (lambda (name)
    (format t "hello, ~a!~%" name)))

```

また、以下のように```lambda```を省略可能である。

```lisp

* (defun hello (name)
    (format t "hello, ~a!~%" name))

* (hello "yamamoto")

hello, yamamoto!
```
***


## 4. 数式
演算子を前に記述する前置記法である。

```lisp
; 足し算
* (+ 1 2)
; 引き算
* (- 1 2)
; 掛け算
* (* 1 2)
; 割算
* (/ 1 2)
```


***

4. フロー制御
***



<a id="ID_1"></a>

## install

- Windowsバージョンのインストール

```https://github.com/roswell/roswell/wiki/Installation```から

roswell_<version>_i686.zip for 64bit
roswell_<version>_amd64.zip for 32bit

自分のpcに合うものをインストール。

- セットアップ

> ros setup


## Common Lispの基本
コマンドプロンプトを起動させて```ros run```を打ち込む。


```lisp
> ros run
* (format t "Helo World~%")
Helo World
NIL
```

### コメントアウト

- 1行 

``` lisp
;コメントアウトだよ～
```

- 複数行

``` lisp
#|
     コメントアウトだよ～
     コメントアウトだよ～
|#
```

## ファイル操作

### ファイルの読み込み

```(load "lisp.lsp")```

















