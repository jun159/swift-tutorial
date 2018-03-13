# Hello World

## Variables & Datatypes
* Do not have to declare datatypes

```swift
var age = 20       
var line = "Hello world" 
var pi = 3.14

// When you print something, it will automatically add new line "\n"
print(age)
print(sent)
```

## Constants 
* Variables are immutable; can be updated
* Use constant if you do not want the value to change

```swift
let age = 16
age = 20  // Error, cannot change constant value
```

## Multiple Assignment
* Instead of having different assignments in multiple lines, we can simply write it with one line.

```swift
var age1 = 16
var age2 = 17
var age3 = 18

var (age1, age2, age3) = (16, 17 18)
```

## Arithmetic Operators
* Declare variables as float/double to get decimal values.

```swift
var num1 = 10
var num2 = 15

num1 + num2
num1 - num2
num1 * num2
num1 / num2   
num1 % num2

num1 += 2
num1 -= 3

var line = "Hello \"World\""
```

## Conditional Statements
* No brackets for conditions

```swift
if isRainy = true {
  print("Bring an umbrella")
} else {
  print("Wear shorts")
}

if age == 30 || age < 17 {
  print("Hello")
}
```

## Arrays
* List of values with the same datatype

```swift
// Initialize array
var shoppingList = ["Apples", "Oranges", "Bananas"]
print(shoppingList[0])
print(shoppingList)

shoppingList.append("Milk")   // Add new item
shoppingList.count            // Size
shoppingList.first            // First item: Apples
shoppingList.last             // Last item: Milk
shoppingList.remove(0)        // First item becomes Oranges
shoppingList.removeAll()      // Remove all
shoppingList[1] = "Grape"     // Assign new value

// Empty array
var newArr = [int]()
newArr.append(5)
newArr.append(10)
```

## Dictionaries
