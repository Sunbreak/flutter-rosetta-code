Introspection
----------------------------------------------------------------

https://rosettacode.org/wiki/Introspection

// TODO

Annotation
----------------------------------------------------------------

// TODO

Reflection
----------------------------------------------------------------

https://rosettacode.org/wiki/Reflection

- https://rosettacode.org/wiki/Reflection/Get_source
- https://rosettacode.org/wiki/Reflection/List_methods
- https://rosettacode.org/wiki/Reflection/List_properties

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

- Dart/VM
```dart
import 'dart:mirrors';

class Parent {
  final parentLabel = 'parentValue';
  String parentFunction() => 'parentResult';
}

class Child extends Parent {
  final childLabel = 'childValue';
  String childFunction() => 'childResult';
}

void main() {
    var childInstMir = reflect(Child());
    var childClzMir = childInstMir.type;
    for (var decl in childClzMir.declarations.entries) {
      print('${decl.key}, ${decl.value}');
    }
    var parentClzMir = childClzMir.superclass!;
    for (var decl in parentClzMir.declarations.entries) {
      print('${decl.key}, ${decl.value}');
    }
}
```

- Dart/JS

```dart
// TODO
```
</td>
<td>

- Dart/VM
```
Symbol("childLabel"), VariableMirror on 'childLabel'
Symbol("childFunction"), MethodMirror on 'childFunction'
Symbol("Child"), MethodMirror on 'Child'
Symbol("parentLabel"), VariableMirror on 'parentLabel'
Symbol("parentFunction"), MethodMirror on 'parentFunction'
Symbol("Parent"), MethodMirror on 'Parent'
```

- Dart/JS
```
```
</td>
</tr>

<tr>
<td>Kotlin</td>
<td>

<!---------------- Kotlin ---------------->
- Kotlin/JVM
```kotlin
import kotlin.reflect.full.memberFunctions
import kotlin.reflect.full.memberProperties

open class Parent {
    val parentLabel = "parentValue"
    fun parentFunction() = "parentResult"
}

class Child : Parent() {
    val childLabel = "childValue"
    fun childFunction() = "childResult"
}

fun main() {
    for (property in Child::class.memberProperties) {
        println("property $property")
    }
    for (function in Child::class.memberFunctions) {
        println("function $function")
    }
}
```

- Kotlin/Native
```kotlin
// https://github.com/Kotlin/kotlinx.serialization/issues/749
// TODO
```

- Kotlin/JS
```kotlin
// TODO
```
</td>
<td>

- Kotlin/JVM
```
property val Child.childLabel: kotlin.String
property val Child.parentLabel: kotlin.String
function fun Child.childFunction(): kotlin.String
function fun Child.equals(kotlin.Any?): kotlin.Boolean
function fun Child.hashCode(): kotlin.Int
function fun Child.parentFunction(): kotlin.String
function fun Child.toString(): kotlin.String
```

- Kotlin/Native
```
```

- Kotlin/JS
```
```
</td>
</tr>

<tr>
<td>Swift</td>
<td>

<!---------------- Swift ---------------->
```swift
class Parent {
    let parentLabel = "parentValue"
    func parentFunction() -> String {
        return "parentResult"
    }
}

class Child: Parent {
    let childLabel = "childValue"
    func childFunction() -> String {
        return "childResult"
    }
}

let childMirror = Mirror(reflecting: Child())
for case let (label?, value) in childMirror.children {
  print("\(label), \(value)")
}
let parentMirror = childMirror.superclassMirror!
for case let (label?, value) in parentMirror.children {
  print("\(label), \(value)")
}
```
</td>
<td>

```
childProperty, childProperty
parentProperty, parentProperty
```
</td>
</tr>

</table>