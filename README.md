  # SwiftCodingCheatSheet

<table>
<td>

- Array
  ```
  [Int](1...3) // [1, 2, 3]
  [1, 2] + [3] // [1, 2, 3]

  ```

- Array fast remove
  ```
  arr.swapAt(index, arr.count-1)
  arr.removeLast()
  ```

- 2D Array
  ```
  var arr3x3 = Array(repeating: [Int](0..<3), count:3)
  var arrRow1 = arr3x3[1]
  arrRow1[1] = 4
  arr3x3[1] = arrRow1 // must set back
  // arr3x3[1][1] = 4
  ```

- Array as Queue
  ```
  arr.first, arr.last
  if !arr.isEmpty {
    let f = arr.removeFirst()
    //let e = arr.removeLast()
  }
  arr.remove(at: i)
  arr.insert(e, at: 0)
  arr.append(e)
  ```

- Sub Array
  ```
  // arr: [1, 2, 3, 4]
  // [3, 4]
  var rest: ArraySlice = arr.dropFirst(2) 
  rest = arr[2..<array.count] //arr[2...array.count-1]
  let restArr = Array(rest)
  ```

- String
  ```
  str.count
  str.append("a") // str += "b"
  // get character at index
  // str[str.index(str.startIndex, offsetBy:index)]
  let arr = Array(str); arr[index] ✅
  ```

- String <-> Int
  ```
  Int(str)
  "\(i)"
  ```

- Character
  ```
  for (i, c) in str.enumerated() where c == " " {
    let a = Int(c.asciiValue! /*UInt8?*/)
  }
  for c in str.unicodeScalars { 
    let _ = Int(c.value /*UInt32*/) 
  }
  ```

- Reorder
  ```
  var arr = [1, 3, 2]
  arr.sort()// mutating func sort()
  arr.sort(by: >) // [3, 2, 1] 
  let sorted = arr.sorted() // func sorted() -> [Element]

  reverse() / reversed() / shuffle() / shuffled() 
  ```

</td>
<!--  -------------------------------------------------------------------------------------------------------------------------------  -->
<td>

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
  for i in stride(from: 2, through: 0, by: -1) {} // 2 1 0
  for (i, element) in arr.enumerated() {}
  for (i, element) in arr.enumerated() where element > 3 {}

  let sum = nums.reduce(0, { x, y in
      x ^ y
  }) // nums.reduce(0, ^)


  ```

- Template
  ```
  func dfs(_ result: inout [[Int]],
    _ path: inout [Int],
    _ visited: inout [Bool],
    _ arr: [Int], _ index: Int) {
    // if end condition { result.append(path); return }
    for i in 0..<arr.count {
        // if should filter out { continue }
        visited[i] = true
        path.append(nums[i])
        dfs(&result, &path, &visited, arr, i+1)
        path.removeLast()
        visited[i] = false
    }
  }
  ```

</td>  
</table>
