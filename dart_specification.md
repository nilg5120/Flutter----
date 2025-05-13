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
final record1 = (300,"cake");
```
### ジェネリクス
```dart
```
### 演算子
```dart
int sum = 5 + 3; // 足し算
int difference = 5 - 3; // 引き算
int product = 5 * 3; // 掛け算
double quotient = 5 / 3; // 割り算
int remainder = 5 % 3; // 割り算の余り
```
### 条件分岐
```dart
//if文
if (age >= 18) {
  print('Adult');
} else {
  print('Minor');
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