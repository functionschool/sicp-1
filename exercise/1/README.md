# 第一章 #
介紹 scheme 的語法，執行順序，
還簡單帶我們思考用不同的執行順序會發生什麼事。

## 1-1 scheme 語法與執行
介紹 scheme 的語法，執行順序。
區分函數和 special form，
special form 是必須的，必須不對某一部份求值，
否則無法對遞迴會無法結束。

這章沒什麼寫 code，都人腦 compile 即可。
只有牛頓法開根號當第一個程式，就手癢寫了很多。
最後介紹巢狀定義函數的時候又把牛頓法重寫一次，
即在大函數裡定義小函數。
（因為 lisp 的語法特性，不這樣寫會看得很累。）
至此明白王垠說過的 *在大的函數裡使用小的工具函數* 。

  - [scheme 版本](newton-sqrt.sch)
  - [emacs lisp 版本](newton-sqrt.el)
  
## 1-2 程序
這章在講遞迴和迴圈，介紹其實尾端遞迴可以看成一種迴圈。
（以後提到迴圈就是指尾端遞迴。）
雖然只有少部份語言實作了尾端遞迴優化。
雖然二者是互通的，但要人腦翻譯有一點難度，
這章要我們互翻迴圈和遞迴。
但有時候就是遞迴比較直覺，尤其是樹狀遞迴 (tree recursion) 。

很多程式開始出現需要遞迴，
我覺得如果在遞迴或迴圈每次都定義一次函數會太麻煩，
於是把該部份獨立出來成一個子函數，和其它輔助函數在同一層。
一般取名為 iter 或 recur。
可能二個都定義，想用哪個就改最後一行呼叫哪個。

  - [簡單階乘](fact.sch)
  - 找零錢問題： 這題覺得很有趣，就寫成
    [scheme](make-change.sch) [elisp](make-change.el) 
    [javascript](make-change.js) 三種版本。
  - [sin 三角函數](sine.sch)
  - [帕斯卡三角形](pascal-tringle.sch) 卡蠻久的，
    最後研究了 numbbbbb 的程式才算出來。
  - [費氏數列](fib.sch)
  
### 1-2-4 [快速冪](fast-expt.md)
就是將複雜度 n 簡化為 log n，包括次方和費氏數列。
算是簡單認識最佳化吧。
之前樹狀遞迴就有討論到，樹狀遞迴可能效率會很差；
像有樹狀遞迴算費氏數列。

### 1-2-5 [因數與質數](gcd.md)
探討了最大公因數、質數判斷等問題，
還介紹了用來判斷質數的不確定演算法。

## 1-3 函數式編程
這章介紹函數式編程的技巧。

### 1-3-1 [抽像化過程](sum-integer.md)
讓函數部份的行為由使用者決定，
就不用定義多個相似的函數。

### 1-3-2 , 1-3-3 [高階函數](half-root.md)
介紹高階函數技巧，包括將函數做為參數、做為返回值，
及 lambda表達式。