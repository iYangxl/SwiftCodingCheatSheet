# SwiftCodingCheatSheet

- String <-> Int
```
Int(str)
"\(i)"
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

- Array fast remove
```
arr.swapAt(index, arr.count-1)
arr.removeLast()
```

- Dictionary
```
var dic = [String: Int]()
if let _ = dic[key] {
  // dic.removeValue(forKey:key)
  dic[key] = nil
}
```

- Random
```
Int.random(in: 0..<6)
arr.randomElement()
```
