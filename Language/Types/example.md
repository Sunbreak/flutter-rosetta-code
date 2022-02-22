# Strings

https://rosettacode.org/wiki/Category:String_manipulation

Literals/String
----------------------------------------------------------------

https://www.rosettacode.org/wiki/Literals/String

<table>

<tr>
<td></td>
<td>Code</td>
<td>Result</td>
</tr>

<tr>
<td>Dart</td>
<td>

<!---------------- Dart ---------------->
```dart
const plain = 'plain';
const json = '''
{
  "key": "value",
}
''';

void main() {
  print('plain $plain');
  print('json $json');
}
```
</td>
<td>

```
plain plain
json {
  "key": "value",
}
```
</td>
</tr>

<tr>
<td>Kotlin</td>
<td>

<!---------------- Kotlin ---------------->
```kotlin
val plain = "plain"
val json = """
{
  "key": "value",
}
"""

fun main() {
    println("plain $plain")
    println("json $json")
}
```
</td>
<td>

```
plain plain
json 
{
  "key": "value",
}
```
</td>
</tr>

<tr>
<td>Swift</td>
<td>

<!---------------- Swift ---------------->
```swift
let plain = "plain"
let json = """
{
  "key": "value",
}
"""

print("plain \(plain)")
print("json \(json)")
```
</td>
<td>

```
plain plain
json {
  "key": "value",
}
```
</td>
</tr>

</table>

Character codes
----------------------------------------------------------------

https://rosettacode.org/wiki/Character_codes

<table>

<tr>
<td></td>
<td>Code</td>
<td>Result</td>
</tr>

<tr>
<td>Dart</td>
<td>

<!---------------- Dart ---------------->
```dart
const c0 = 'a';
final c1 = String.fromCharCode(c0.codeUnitAt(0) + 2);

void main() {
    print("$c0, ${c0.codeUnits}");
    print("$c1, ${c1.codeUnits}");
}
```
</td>
<td>

```
a, [97]
c, [99]
```
</td>
</tr>

<tr>
<td>Kotlin</td>
<td>

<!---------------- Kotlin ---------------->
```kotlin
val c0 = 'a'
val c1 = (c0.code + 2).toChar()

fun main() {
    println("$c0, ${c0.code}")
    println("$c1, ${c1.code}")
}
```
</td>
<td>

```
a, 97
c, 99
```
</td>
</tr>

<tr>
<td>Swift</td>
<td>

<!---------------- Swift ---------------->
```swift
let c0: UnicodeScalar = "a"
let c1 = UnicodeScalar(c0.value + 2)!

print("\(c0), \(c0.value)")
print("\(c1), \(c1.value)")
```
</td>
<td>

```
a, 97
c, 99
```
</td>
</tr>

</table>

# Collections

https://rosettacode.org/wiki/Collections

- Array: https://rosettacode.org/wiki/Array
- Set: https://rosettacode.org/wiki/Set
- Associative array: https://rosettacode.org/wiki/Associative_array

<table>

<tr>
<td></td>
<td>Code</td>
<td>Result</td>
</tr>

<tr>
<td>Dart</td>
<td>

<!---------------- Dart ---------------->
```dart
const list = [1, 2, 3];
const set = {'1', 'b', 'c'};
const map = {
    1: 'a',
    2: 'b',
    3: 'c',
};

void main() {
  print('list $list');
  print('set $set');
  print('map $map');
}
```
</td>
<td>

```
list [1, 2, 3]
set {1, b, c}
map {1: a, 2: b, 3: c}
```
</td>
</tr>

<tr>
<td>Kotlin</td>
<td>

<!---------------- Kotlin ---------------->
```kotlin
val array = arrayOf(-1, -2, -3)
val list = listOf(1, 2, 3)
val sequence = sequenceOf(10, 20, 30)
val set = setOf("a", "b", "c")
val map = mapOf(
    1 to "a",
    2 to "b",
    3 to "c",
)

fun main() {
    println("array $array")
    println("list $list")
    println("sequence $sequence")
    println("set $set")
    println("map $map")
}
```
</td>
<td>

- Kotlin/JVM

```
array [Ljava.lang.Integer;@7a4f0f29
list [1, 2, 3]
sequence kotlin.collections.ArraysKt___ArraysKt$asSequence$$inlined$Sequence$1@77a567e1
set [a, b, c]
map {1=a, 2=b, 3=c}
```

- Kotlin/Native

```
array kotlin.Array@8c0d158
list [1, 2, 3]
sequence kotlin.collections.Sequence$1@8c0d248
set [a, b, c]
map {1=a, 2=b, 3=c}
```

- Kotlin/JS

```
array -1,-2,-3
list [1, 2, 3]
sequence [object Object]
set [a, b, c]
map {1=a, 2=b, 3=c}
```
</td>
</tr>

<tr>
<td>Swift</td>
<td>

<!---------------- Swift ---------------->
```swift
let array: Array = [1, 2, 3]
let set: Set = ["a", "b", "c"]
let map = [
    1: "a",
    2: "b",
    3: "c"
]

print("array \(array)")
print("set \(set)")
print("map \(map)")
```
</td>
<td>

```
array [1, 2, 3]
set ["c", "a", "b"]
map [3: "c", 1: "a", 2: "b"]
```
</td>
</tr>

</table>
