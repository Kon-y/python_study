# Python 学習Ⅰ

## コマンド実行

```python
python3 {command}
```

## 標準出力

シングルクォーテーションもしくはダブルクォーテーションで囲む。

```python
print('表示したい文字列') or print("表示したい文字列")
```

## コメント

\# ← 先頭に入れる。

## 数値

数値はクォーテーションでは囲まない。シングル(ダブル)クォーテーションで囲むと文字列になる。

```python
print(3) or print (3 + 7) or print(7 - 3)
```

## その他の計算

```python
print(3 * 7)  3 × 7を表している。
print(3 / 2)  3 ÷ 2を表している。
print(7 % 3)  7 ÷ 3 = 2 余 1 ← この「余(1)を表示させる計算式」
```

## 変数

変数 = 値(もしくは文字列)で定義する。
変数値を取り出す。クォーテーションで囲むと変数名が文字列として表示される。

```python
name = 'kon'
print(name)      print('name') → nameと出力されてしまう。
```

## 変数名の付け方

date ← 英単語を用いる。
user_name ← 2語以上の場合はアンダーバーで区切る。
1user ← 先頭が数字は”NG”
日本語もNG

## 変数の予約語

以下の名前はPythonの予約語になっているため、変数として使用できない。

```console
False class finally is return None continue for lambda try
True def from nonlocal while and del global not with
as elif if or yield assert else import pass
break except in raise
```

## 省略

計算式を右のように省略して書ける。

```console
x  = x + 10 -> x += 10
x = x - 10 -> x -= 10
x = x * 10 -> x *= 10
x = x / 10 -> x /= 10
x = x % 10 -> x %= 10
```

## 文字列の連結

print('hello ' + 'Python') -> hello Pythonと表示される。
変数を使用した連結は・・・

```python
name = 'kon'
print('hello ' + name) -> hello konと表示される。
```

## 型変換 str

異なる型同士の連結はできない。
例：

```console
price = 100
print('リンゴの価格は' + price + '円です)
　　　　文字列型　　　　　数値型　　文字列型
エラーメッセージが出力される。
```

異なる型を変換させ表示させるとOK
例：
price = 100
print('リンゴの価格は' + str(price) + '円です')
                        文字列型に変換され出力される。

## 型変換 int

strとは反対で、文字列を数値型に変換する。
例：

```console
count = '3'
price = 100
total_price = price * int(count)
                      文字列型を数値型に変換する。
print(total_price)
```

## if文

基本形式(多分これを覚えとけばどこでも通じると思われ。)
例：

```python
score = 100
if score == 100 :　←ダブルコロンお忘れなく。
    print('大変よくできました！')
    print('次も頑張りましょう！')
```

　悪例

```python
    if score == 100 :　←ダブルコロンお忘れなく。
        print('大変よくできました！')
    print('次も頑張りましょう！')
     └> インデントがないとif文の外とみなされるため、条件に関係なく「次も頑張りましょう！」と出力される。
```

※比較演算子解説
・等しいか調べるときに使用する。
　x == y → 左右の値が等しいと時成り立つ
　x != y → 左右の値が等しくない時成り立つ
・大小を比べる
　<  → 右辺の方が大きいときTrue
　<= → 右辺の方が大きい又は等しいときTrue
　>  → 右辺の方が小さいときTrue
　>= → 右辺の方が小さい又は等しいときTrue

## 真偽値

```python
score = 100
if score == 100 :
    print('よくできました！')
```

結果：よくできました！と出力される。
    ↓

```python
score = 100
print(score == 100)　　  print(score == 50)
```

結果：Trueと出力される。      Falseと出力される。

True or False ← 真偽値

## 条件に合致しない時の処理

条件式に合致しない場合の処理を含める場合はelseを使う。
例：

```python
score = 50
if score == 100 :
    print('よくできました！')　←　条件式がTrueの場合に出力される。
else : ←「:」お忘れなく。
    print('頑張りましょう')　　←　条件式がFalseの場合に出力される。
```

## 条件式を組み合わせよう(and編)

2つの条件を組み合わせた式を作る。
True and True -> True
True and False -> False
False and True -> True
False and Flase -> False
例：

```python
time = 14
if time > 10 and time < 18 :　←　timeが10より大きく、18より小さければ
    print('就業時間です。')　←　「就業時間です」と表示させる。
```

## 条件式を組み合わせよう(or編)

片方のみTrueが成立するような条件式を作る。
True or True -> True
True or False -> True
False or True -> True
False or Flase -> False
例：

```python
time = 15
if time == 10 or time == 15 :　← timeが10もしくは15だった場合
    print('おやつの時間です')　←　「おやつの時間です」と表示させる。
```

## 条件式を組み合わせよう(not編)

否定をするときに使用する。
例：

```python
time = 9
if not time == 18 :　←　timeが18以外だった場合
    print('退社時刻ではありません')　←　「退社時刻ではありません」と表示させる。
```

## 入力を受け取ろう。(コンソールで入力された値を代入する。)

```python
apple_price = 200
input_count = input('...りんごの個数を入力してください：')
count = int(input_count)　← 入力してもらった値をcount変数に代入している。
total_price = apple_price * count
print('支払い金額は' + str(total_price) + '円です')
```

## 条件分岐

pythonに似ている。

```python
if <条件> :
    処理

elif <条件> :
    処理

else :
    処理
```

---

## Python 学習Ⅱ

目的：複数のデータを管理する方法や、同じ処理を自動で繰り返す「繰り返し処理」といった、
　　　プログラミングで必須の知識を学びます。

## リスト

データを個別に管理する方法と、複数のデータをまとめて管理する方法
リストの作り方
[ 要素1, 要素2, 要素3 ]
      └> データ(要素)はコンマで区切る。最後のデータ(要素)にはコンマを使用しない。

・文字列のリスト
['apple','curry','sushi','tenpura']

・数値のリスト
[1,2,3,4,5,6,7,8,9,]

・文字列と数値のリスト
['apple','sushi',1,2,3]

## リストを変数に代入しよう

リストも変数に代入できる。

```python
foods = ['pasta','curry','sushi']
print(foods)
```

pasta curry sushiが1個ずつ出力される。

## リストから指定した文言を出力させる

printで何番目の文字列を出力しているか指定している。
例：

```Python
cliches = [
"At the end of the day",
"Having said that",
"The fact of the matter is",
"Be that as it may",
"The bottom line is",
"If you will",
]
print(cliches[3])
```

## リストの要素を取得しよう

リストの要素は前から順番に0、１、２と数字(インデックス番号)が割り当てられている。

```python
['apple','curry','sushi','tenpura']
　└> 0　　└> 1　　　└> 2　　└> 3　　← インデックス番号
```

例：

```Python
foods = ['apple','curry','sushi','tenpura']
print('好きな食べ物は' + foods[2] + 'です')　← 「好きな食べ物はsushiです」と出力される。
　　　　　　　　　　　　　　　　└> sushiが抽出・出力される。
```

## リストの要素を更新しよう

「リスト[インデックス番号] = 値」とすることで、リストの指定したインデックス番号の要素を更新することができる。
例：

```python
foods = ['apple','curry','sushi','tenpura']
foods[1] = 'pizza'
      └> インデックス番号1の要素(curry)を更新(pizza)
print(foods)
　└> ['apple','pizza','sushi','tenpura']と出力される。
```

## リストに要素を追加

「リスト.append(値)」とすることで、すでに定義されているリストの末尾に新たな要素を追加することができる。
　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　~~~~ ここ注意
例：

```python
foods = ['apple','curry','sushi','tenpura']
foods.append('pizza')
      └> リストの末尾に要素(pizza)を追加
print(foods)
　└> ['apple','curry','sushi','tenpura','pizza']と出力される。
```

```console
## for文
## 辞書
## 辞書の要素の更新・追加
## for分(2)
## while文
## break
## continue
```

---

## Python 学習Ⅲ

目的：開発をする際に必須となる関数やモジュールについて学習する。
　　　じゃんけんゲームを作りながら知識を身につける。

## 関数とは

ある処理をまとめたプログラムの塊で、printも関数の1つです。
本来、コンソールに文字を出力するためには色々なコードを書く必要がありますが、
printという関数のおかげでprintとだけ書けばいいようになっています。
printの他にもPythonにはいくつかの便利な関数が用意されており、それらを使うと様々な処理を簡単に行うことができます。
また、関数は自分で作ることもできます。
これらの関数を組み合わせることで、プログラムを効率的に作ることができます。

## 関数を作ってみよう

関数は「def 関数名():」のように定義します。関数の処理の内容は、インデント4つを設ける。
def 関数名(): ← 行末にコロンをお忘れなく
    実行する処理
↑↑↑↑ ← インデントを4つ開ける。
例：

```python
def hello():
    print('Hello World')
```

## 関数の使い方

```python
def hello():
    print('Hello World')

hello() ← 関数の呼び出し
```

---

## Python 学習Ⅳ

目的：クラスを学ぼう

## 「もの」を生成する仕組み

ものを生成する為には、まずその「設計図」を用意する必要がある。
設計図のことを「クラス」、もののことを「インスタンス」と呼ぶ。

## インスタンスを生成するステップ

STEP1：クラスを用意する。
STEP2：クラスからインスタンスを生成する。
STEP3：インスタンスに情報を追加する。

## オブジェクトとは何か

Pythonに含まれるものは、数値からモジュールに至るまですべてオブジェクトである。

## クラスの定義

class MenuItem: ← 行末にコロンはお忘れなく
　　　 ↑ クラス名は大文字から始める。

例：

```python
class Person():
    def __init__(self, name);  <- __init__を定義するときの第一引数はselfでなければならない。
        self.name = name
hunter = person('Elmer Fudd')
print('The mighty hunter: ', hunter.name)
```

→ [The mighty hunter:  Elmer Fudd]と出力される。

## クラスの中身

「class MenuItem:」より後の行で、インデントをして書く。

```python
class MenuItem:
    # 実行したい処理を書く
```

例：

```python
class MenuItem:
    pass
     └> 処理がなにもないことを表す。
```

## クラスからインスタンスを生成しよう

クラス名()」とそのクラスを呼び出すことで、クラス（設計図）を用いて新しくインスタンスを生成することができる。
また、「変数名 = クラス名()」とすることで、生成したインスタンスを変数に代入することができる。
例：

```python
class MenuItem:
    pass
menu_item1 = MenuItem() ← MenuItemからインスタンスを生成
　↪ 変数に代入する。
```

## クラスの継承

使いたい既存のクラスを指定し、追加・変更したい一部だけを定義する新しいクラスを作る。
例：Carという空クラスを定義し、YugoというCarのサブクラスを定義する。

```python
class Car():
    def exclaim(self):
        print(I'm a Car!")

class Yugo(Car):
    pass
```

続いてそれぞれのクラスからオブジェクトを作る。

```python
give_me_a_car = Car()       -> 何も表示されない。
give_me_a_yugo = Yugo()     -> 何も表示されない。
give_me_a_car.exclaim()     -> I'm a Car!と表示される。
give_me_a_yugo.exclaim()    -> I'm a Car!と表示される。
```

## メソッドのオーバーライド

親クラスのメソッドを上書き(オーバーライド)する方法

```bash
class Car():
    def exclaim(self):
        print("I'm a Car!")

class Yugo(Car)
    def exclaim(self):
        print(I'm a Yugo[; Much like a Car, but more Yugo-ish.")

give_me_a_car = Car()
give_me_a_yugo = Yugo()
```

上記でオーバーライドしたのはexclaim()メソッドだが、
__init__()を含むあらゆるメソッドをオーバーライドできる。

```bash
class Person():
    def __init__(self, name):
        self.name = name

class MDPerson(Person):
    def __init__(self, name):
        self.name = "Doctor " + name

class JDPerson(Person):
    def __init__(self, name):
        self.name = name + ", Esquire"
person = Person('Fudd')
doctor = MDPerson('Fudd')
lawyer = JDPerson('Fudd')
print(person.name)
print(doctor.name)
print(lawyer.name)
```

親のPersonクラスと同じ引数を取ってオブジェクトに格納されるnameの値を変えている。

## メソッドの追加

子Classは、親Classになかったメソッドを追加することができる。

---

## 第5章

## Pyの化粧箱：モジュール、パッケージ、プログラム

いままでのPythonの対話型インタプリンタの中で以下のようなコードの断片を書いて実行していた。

```bash
print("This interactive snippet works.")
This interactive snippet works.
```

### import sys

```bash
import sys
print('Program arguments:', sys.argv)
```
