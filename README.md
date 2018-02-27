# Swift Style Guide

The coding style guide for Swift

### Naming convention

| Type | Name |
| - | - |
| ID | id |
| ProductID | productID |
| URL | url |
| ImageURL | imageURL |

### Spacing between lines

Prefer

```swift
// Spacing here
var foo = true
// Spacing here
bar.doSomething()
// Spacing here
foo = false
// Spacing here
```

Rather than

```swift

var foo = true
bar.doSomething()
foo = false

```

### Function

Prefer

```swift

// One input and one output.
func foo(var1: String) -> Double { ... }

// One input and multiple outputs.
func foo(var1: String)
throws -> (Double)
-> Int { ... }

// More than one input.
func foo(
  var1: String,
  var2: Int
)
-> Double { ... }

func foo(
  var1: String,
  var2: Int
)
-> (Double)
throws -> Int { ... }

```

Rather than

```swift

func foo(var1: String) throws -> (Double) -> Int { ... }

func foo(var1: String, var2: Int) -> Double { ... }

func foo(var1: String, var2: Int) throws -> (Double) -> Int { ... }

```

#### Always add decimal point for a double number

Prefer

```swift

let price = 12.0

```

Rather than

```swift

let price = 12

```

#### Use immutable by default

Prefer `let`

```swift

let bar = 1

```

Rather than

```swift

var foo = 1

```

Prefer `struct`

```swift

struct Foo { ... }

```

Rather than

```swift

class Foo { ... }

```

#### Always mark access control explicitly at the front most

Prefer

```swift

internal var bar: Bar

internal override func foo() { ... }

```

Rather than

```swift

var bar: Bar

override internal foo() { ... }

```

#### Mark class as final by default and followed right after access control

Prefer

```swift

final class Foo { ... }

public final func bar() { ... }

```

Rather than

```swift

class Foo { ... }

final public func bar() { ... }

```

#### Using `if else`

Prefer

```swift

if
    let name = json?["name"] as? String,
    let age = json?["age"] as? Int {

}
else if
    let firstName = json?["firstName"] as? String,
    let lastName = json?["lastName"] as? String {

}
else {

}

```

#### Using `guard else`

Prefer

```swift

guard
    let text = textField.text,
    !text.isEmpty
else { return }

```

#### Avoid default case while switching

Given an enum

```swift

enum Priority {

  case high, medium, low

}

```

Prefer

```swift

switch priority {

case .high, .medium:

  ...

case .low:

  ...

}

```

Rather than

```swift

switch priority {

case .high, .medium:

  ...

default:

  ...

}

```

#### DO NOT use abbreviation for naming everything except for some acceptable cases

**Acceptable common abbreviation**

| Origin | Abbreviation  |
| - | - |
| character | char |
| arguments | args |
| properties | props |
| information  | info |
| maximum | max |
| minimum | min |

# References

* [GitHub - Swift Style Guide](https://github.com/github/swift-style-guide)
* [Increasing Performance by Reducing Dynamic Dispatch](https://developer.apple.com/swift/blog/?id=27)
