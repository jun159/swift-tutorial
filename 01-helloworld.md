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
* Key-value pairs (keys are all unique)
* Required for JSON etc that is uses key-value pairs

```swift
var myDict = ["blue": "water", "green":"land"]
print(myDict)
print(myDict["blue"])         // Optional: Swift doesn't know if this key exist, do not throw error if doesn't exist
print(myDict["blue"]!)        // Confirm that this key exist, throws error if doesn't exist

myDict["blue"]                // Get value: water
myDict.count                  // Size
myDict["blue"] = "ocean"      // Update new value
myDict["red"] = "bridge"      // Add new value
myDict.removeValue("red")     // Remove a value
myDict.removeAll()            // Remove all
```

## For Loops
* Takes the range (inclusive of last)

```swift
for i in 1...10 {
  print(i)        // Prints 1 2 3 4 5 6 7 8 9 10
}

// Multiples 
for num in stride(5, 50, 5) {
  print(num)      // Prints multiples of 5
}

for num in stride(50, 5, -5) {
  print(num)      // Prints multiples of 5
}

// Iterate array
var shoppingList = ["Apples", "Oranges", "Bananas"]
for item in shoppingList {
  print(item)       // Print: Apples Oranges Bananas
}

// Iterate dictionaries
var myDict = ["blue": "water", "green":"land"]
for item in myDict {
  print(item)        // Print: {key: "blue", value: "water"} {key: "green", value: "land"}
  print(item.key)    // Print keys: blue green
}

for (index, value) in shoppingList.enumerated {
  print(index)      // Prints: 0 Apples 1 Oranges 2 Bananas
  print(value)
}
```

## While Loops
* Always run until condition is false

```swift
var counter = 0

// Normal while loop
while counter < 10 {
  print(counter)
  counter += 1
}

// Repeat while loop
repeat {
  print(counter)
  counter += 1
} while counter < 10
```

## Switch Statements
* Alternative for if-else statements

```swift
var age = 10

switch age {
  case 14 : {
    print("You are 14")
  }
  
  case 16 : {
    print("You are 16")
  }
  
  default : {
    print("Not sure how old you are")
  }
}
```

## Loop Control Statements
* Terminate or skip loop

```swift
for i in 1...10 {
  print(i)
  if i == 5 { 
    break     // Terminates loop
  }
}

for i in 1...10 {
  if i == 5 || i == 6 { 
    continue    // Skips printing 5 and 6
  }
  print(i)
}
```

## Functions
* Set of statements organised to perform specific task

```swift
// Specify the datatype for parameters
func add(num1 : Int, num2 : Int) {
  print(num1 + num2)
}

// Specify the datatype to return using ->
func multiply(num1 : Int, num2 : Int) -> Int {
  return num1 * num2
}

var total = add(num1 : 1, num2 : 2)
print(multiply(num1 : 10, num2 : 2))
```

## Structures
* Encapsulate data by grouping together certain variables

```swift
// Without structure
var name = "Hello"
var latitude = 41.123
var longitude = 42.123

func getLocation(name: String, latitude: Double, longitude: Double) {
  print(name)
}

print(getLocation(name : name, latitude : latitude, longitude : longitude)
```

```swift

// With structure: Instead of creating 3 separate variables, we create 1 variable containing all 3 variables
struct userLocation {
  var name : String
  var latitude : Double
  var longitude : Double
}

var location = userLocation(name : "Hello", latitude : 41.123, longitude : 42.123)
var name = location.name
var latitude = location.latitude
var longitude = location.longitude

func getLocation(loc : userLocation) {
  print(loc.name)
}

print(getLocation(loc : location))
```

## Enum
* Set of constant data (e.g. days of the week)

```swift
enum Direction {
  case North
  case South
  case East
  case West
}

// Without enum
var dir = "North"

// With enum
var dir = Direction.North
```

* Enumeration with Switch
```swift
switch dir {
  case Direction.North : {
      print("Go forward")
  }

  case Direction.South : {
      print("Go backward")
  }
  
  case Direction.East : {
    print("Go right")
  }
  
  case Direction.West : {
    print("Go left")
  }
  
  // No need default case - with enumeration, we only have 4 possible cases
}

// Raw value concept
enum Direction : String {
  case North = "Go forward"
  case South = "Go backward"
  case East = "Go right"
  case West = "Go left"
}

var dir = Direction.North   // North
dir.rawValue                // "Go forward"
```

## Classes and Objects

```swift
class Person {
  var name : String
  var age : Int
  
  init(name : String, age : Int) {
    self.name = name
    self.age = age
  }
  
  func greeting() {
    print("Name: " + self.name + ", Age: " + self.age")
    print("Name: \(self.name), Age: \(self.age)")
  }
}

var person = Person(name : "Hello", age : 10)
var name = person.name
var age = person.age

person.greeting()
```

## Inheritance and Overriding
* Inheritance: Inherit all methods from parent class
* Overriding: Override parent class method

```swift
// Parent
class Parent {
  func parentMethod() {
    print("Parent")
  }
  
  func getName() {
    print("Parent Name")
  }
}

var p = Parent()
p.parentMethod()
p.getName()         // "Parent Name"
```

```swift
// Child
class Child : Parent {
  func childMethod() {
    print("Child")
  }
  
  // Must mention "override", else error
  override func getName() {
    print("Child Name")
  }
}

var c = Child()
c.childMethod()
c.parentMethod()    // Also works
c.getName()         // "Child Name"
```
