# Extensions Examples

## Initial Code
```swift
func abc(value: String) -> String {
	value.map(String.init)
		.sorted(by: <)
		.joined(separator: "")
}

print(abc(value: "zxcasdqwe")) // output: "acdeqswxz"

// ...

protocol ABC {
	func abc() -> String
}
```

## Goal
```swift
extension String: ABC { ... }

print("zxcasdqwe".abc()) // output: "acdeqswxz"
```


## String Solution

<details> 
  <summary>Solution</summary> 

```swift 
extension String: ABC {
	func abc() -> String {
		map(String.init)
			.sorted(by: <)
			.joined(separator: "")
	}
}
```

</details> 


### Extended Example

#### Goal
```swift
extension Int: ABC { ... }

print(9753146286.abc()) // output: "1234566789"
```

#### Int Solution

<details> 
  <summary>Solution</summary> 

```swift 
extension Int: ABC {
	func abc() -> String {
		self.description.abc()
	}
}
```

</details> 


##### Protocol Polymorphism Example
```swift
let abcValues: [ABC] = ["Hello, World!", 975421]

abcValues.forEach { value in
	print(value.abc())
}
// output: 
// " !,HWdellloor\n"
// "124579"
```
