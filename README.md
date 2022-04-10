# SwiftCodingCheatSheet

- Array
```
var arr3x3 = Array(repeating: [Int](repeating:1, count:3), count:3)
var arrRow1 = arr3x3[1]
arrRow1[1] = 2
arr3x3[1] = arrRow1 // must set back
// arr3x3[1][1] = 2
```

- Array fast remove
```
arr.swapAt(index, arr.count-1)
arr.removeLast()
```

- Array as Queue
```
arr.first, arr.last
let f = arr.removeFirst()
let e = arr.removeLast()
arr.insert(e, at: 0)
arr.remove(at: i)
arr.append(e)
arr.isEmpty
```

- Sub Array
```
// arr: [1, 2, 3, 4]
// [3, 4]
let rest: ArraySlice = arr.dropFirst(2) //  arr[2..<array.count] //  arr[2...array.count-1]
let restArr = Array(rest)
```

- String
```
str.count
str.append("a") // str += "b"
```

- String <-> Int
```
Int(str)
"\(i)"
```

- Dictionary
```
var dic = [String: Int]()
if let _ = dic[key] {
  dic[key] = nil   // dic.removeValue(forKey:key)
}
```

- Set
```
var s = Set(arr)
s.isEmpty
s.contains(e)
s.insert(e)
s.remove(e)
union、intersection、subtracting、symmetricDifference
```

- Random
```
Int.random(in: 0..<6)
arr.randomElement()
```

- Numbers

```
max(4, 2, 1, 3, 5)
min(1.0, 2.1)
```

- Enumeration

```
for i in 1...10 {}
for i in stride(from:0, to:10, by:2){} // 0 2 4 6 8
for countdown in stride(from: 3, through: 0, by: -1) {} // 3 2 1 0
for (index, element) in arr.enumerated() {}
for (index, element) in arr.enumerated() where element > 3 {}
for (i, c) in str.enumerated() where c == " " {}

let sum = nums.reduce(0, { x, y in
    x ^ y
}) // nums.reduce(0, ^)


```
