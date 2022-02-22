Call a function
----------------------------------------------------------------

https://rosettacode.org/wiki/Call_a_function

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
void foo(
  String param0, {
  String? namedParam1,
}) => print('$param0, $namedParam1');

String bar(
  String param0, [
  String? optionalParam1,
]) {
  print('$param0, $optionalParam1');
  return optionalParam1 ?? '--';
}

void main() {
  foo('foo0');
  foo('foo0', namedParam1: 'foo1');
  final a = bar('bar0');
  print('optionalParam1 $a');
  final b = bar('bar0', 'bar1');
  print('optionalParam1 $b');
}
```
</td>
<td>

```
foo0, null
foo0, foo1
bar0, null
optionalParam1 --
bar0, bar1
optionalParam1 bar1
```
</td>
</tr>

<tr>
<td>Kotlin</td>
<td>

<!---------------- Kotlin ---------------->
```kotlin
fun foo(
    param0: String,
    param1: String,
) = println("$param0, $param1")

fun bar(
    param0: String,
    optionalParam1: String? = null,
): String {
    println("$param0, $optionalParam1")
    return optionalParam1 ?: "--"
}

fun main() {
    foo("foo0", "foo1")
    foo(param0 = "foo0", "foo1")
    val a = bar("bar0")
    println("optionalParam1 $a")
    val b = bar("bar0", optionalParam1 = "bar1")
    println("optionalParam1 $b")
}
```
</td>
<td>

```
foo0, foo1
foo0, foo1
bar0, null
optionalParam1 --
bar0, bar1
optionalParam1 bar1
```
</td>
</tr>

<tr>
<td>Swift</td>
<td>

<!---------------- Swift ---------------->
```swift
func foo(
    _ param0: String,
    argName1 param1: String
) {
    print("\(param0), \(param1)")
}

func bar(
    argName0 param0: String,
    argName1 optionalParam1: String? = nil
) -> String {
    print("\(param0), \(optionalParam1)")
    return optionalParam1 ?? "--"
}

foo("foo0", argName1: "foo1")
let a = bar(argName0: "bar0")
print("optionalParam1 \(a)")
let b = bar(argName0: "bar0", argName1: "bar1")
print("optionalParam1 \(b)")
```
</td>
<td>

```
foo0, foo1
bar0, nil
optionalParam1 --
bar0, Optional("bar1")
optionalParam1 bar1
```
</td>
</tr>

</table>

First class function
----------------------------------------------------------------

https://rosettacode.org/wiki/First-class_functions

Anonymous recursion
----------------------------------------------------------------

https://rosettacode.org/wiki/Anonymous_recursion

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
import 'package:quiver/iterables.dart' show range;

final int Function(int) fib = () {
  int f(int n) {
    assert(n >= 0, 'fib: no negative numbers');
    return n < 2 ? 1 : f(n - 1) + f(n - 2);
  }
  return f;
}();

void main() {
  for (var i in range(0, 11).cast()) {
    print(fib(i));
  }
}
```
</td>
<td>

```
1
1
2
3
5
8
13
21
34
55
89
```
</td>
</tr>

<tr>
<td>Kotlin</td>
<td>

<!---------------- Kotlin ---------------->
```kotlin
val fib: (Int) -> Int = run {
    fun f(n: Int): Int {
        require(n >= 0) { "fib: no negative numbers" }
        return if (n < 2) 1 else f(n - 1) + f(n - 2)
    }
    ::f
}

fun main() {
    for (i in 0..10) {
        println("${fib(i)}")
    }
}
```
</td>
<td>

```
1
1
2
3
5
8
13
21
34
55
89
```
</td>
</tr>

<tr>
<td>Swift</td>
<td>

<!---------------- Swift ---------------->
```swift
let fib: (Int) -> Int = {
    func f(_ n: Int) -> Int {
        assert(n >= 0, "fib: no negative numbers")
        return n < 2 ? 1 : f(n - 1) + f(n - 2)
    }
    return f
}()

for i in 0...10 {
    print(fib(i))
}
```
</td>
<td>

```
1
1
2
3
5
8
13
21
34
55
89
```
</td>
</tr>

</table>