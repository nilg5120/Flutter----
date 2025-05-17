# Dartの言語仕様
## 変数と型推論
### finalとconst
```dart
final String name = 'John'; // 変更不可
const String constantName = 'Doe'; // コンパイル時定数
//late
late String description; // 後で初期化する変数を明示的に宣言
description = 'This is a late variable.'; // 後で初期化
```
### 型
```dart
//組み込み型
int age = 30; // 整数型
double height = 1.75; // 浮動小数点型
String greeting = 'Hello, Dart!'; // 文字列型
String quote = "シングルクォートでもダブルクォートでもOK";
String variable = "${greeting}"; //${}で変数を表す。Hello, Dart!が入ってるよ
String concat = 'Hello, ' 'Dart!'; //クォートが隣り合うとくっついて出力されるHello, Dart!
String multiLine = """
    1行目
    2行目
    3行目
"""; //複数行をデータとして持てる。
String escapeSpecialCharacter = r"Hello,/nDart!";//特殊文字の無効化
bool isActive = true; // 真偽値型
```
### コレクション
```dart
//リスト
List<String> fruits = ['Apple', 'Banana', 'Banana']; // 文字列のリスト
//セット
Set<String> uniqueFruits = {'Apple', 'Banana', 'Cherry'}; // 重複しない文字列の集合
//マップ
Map<String, int> scores = {'Alice': 90, 'Bob': 85}; // 文字列をキー、整数を値とするマップ
//タプル
final record1 = (300,"cake");//複数の型が異なる値をまとめる
```
### ジェネリクス
```dart
class Foo<T>{//慣習的に"T"などの1文字で表す
  T? firstOrNull<T>(List<T> list){
    return null;
  }
}
```
### 演算子
```dart
int sum = 5 + 3; // 足し算
int difference = 5 - 3; // 引き算
int product = 5 * 3; // 掛け算
double quotient = 5 / 3; // 割り算
int remainder = 5 % 3; // 割り算の余り

//インクリメントデクリメント
a = b++
a = ++b
a = b--
a = --b

//比較演算子
(2==2)
(2!=1)
(2>1)
(2>=1)
(2<1)
(2<=1)

//三項演算子
1=1?true:false;//この場合は左、違えば右
```
### カスケード記法
```dart
// カスケード記法を使ってプロパティにアクセス..
final StringBuffer buffer = StringBuffer()
    ..write('Hello, ')
    ..write('Dart!');
print(buffer.toString());
```
### spread演算子
```dart
// spread演算子を使ってリストやマップを展開
List<String> fruits = ['Apple', 'Banana', 'Cherry'];
List<String> moreFruits = ['Durian', 'Elderberry'];
List<String> allFruits = [...fruits, ...moreFruits];
print(allFruits);

// マップの展開
Map<String, int> scores = {'Alice': 90, 'Bob': 85};
Map<String, int> moreScores = {'Charlie': 80};
Map<String, int> allScores = {...scores, ...moreScores};
print(allScores);
```
### 制御構文演算子
```dart
//コレクションのリテラル内でIfやforを使う
List<String> fruits = ['Apple', 'Banana', 'Cherry'];
List<String> filteredFruits = [
  for (var fruit in fruits) if (fruit.startsWith('A')) fruit
];

```
### 制御構文
```dart
//if文
if (age >= 18) {
  print('Adult');
} else {
  print('Minor');
}
//if-case文
Object value = 'hello';

if (value case String text) {
  print('文字列です: $text');
}
//if-case-when文
if (value case int number when number > 0) {
  print('正の整数です: $number');
} else if (value case int number when number < 0) {
  print('負の整数です: $number');
} else {
  print('整数ではありません');
}
//switch文
switch(color){
  case 'red':
    print('red');
    break;
  case 'blue':
    print('blue');
  default :
    print('default');
}
```
### ループ
```dart
//for文
for (int i = 0; i < 5; i++) {
  print(i);
}
//for-in文
List<String> names = ['Alice', 'Bob', 'Charlie'];
for (String name in names) {
  print(name);
}
//while文
int count = 0;
while (count < 5) {
  print(count);
  count++;
}
//do-while文
int count = 0;
do {
  print(count);
  count++;
} while (count < 5);
//break文
for (int i = 0; i < 5; i++) {
  if (i == 3) {
    break; // ループを終了
  }
  print(i);
}
//continue文

for (int i = 0; i < 5; i++) {
  if (i == 3) {
    continue; // 次の反復にスキップ
  }
  print(i);
}
//return文
int add(int a, int b) {
  return a + b; // 関数から値を返す
}
//yield文
Iterable<int> generateNumbers(int n) sync* {
  for (int i = 0; i < n; i++) {
    yield i; // 値を生成
  }
}
```