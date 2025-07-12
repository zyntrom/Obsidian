## **Java Basic Syntax Table**

| **Concept**          | **Syntax / Example**                      | **Notes**                                                   |
| -------------------- | ----------------------------------------- | ----------------------------------------------------------- |
| Variable Declaration | `int x = 5;`                              | Types: `int`, `long`, `double`, `boolean`, `char`, `String` |
| Array                | `int[] arr = new int[5];`                 | 0-based indexing                                            |
| 2D Array             | `int[][] matrix = new int[3][4];`         | Nested loops for traversal                                  |
| Input Scanner        | `Scanner sc = new Scanner(System.in);`    | `sc.nextInt()`, `sc.nextLine()`                             |
| Print Output         | `System.out.println("Hello");`            | `println`, `print`, `printf`                                |
| If Condition         | `if (a > b) { ... }`                      | `else if`, `else` supported                                 |
| Switch               | `switch(x) { case 1: ... break; }`        | Always `break` unless intentional fallthrough               |
| For Loop             | `for (int i = 0; i < n; i++) { ... }`     | Use `arr.length` for arrays                                 |
| While Loop           | `while (condition) { ... }`               | Entry-checked loop                                          |
| Do-While Loop        | `do { ... } while (condition);`           | Exit-checked loop                                           |
| Function             | `int add(int a, int b) { return a + b; }` | Return type required                                        |
| Class                | `class MyClass { ... }`                   | File name = Class name (for public)                         |
| Object Creation      | `MyClass obj = new MyClass();`            | Constructor used                                            |
| Try-Catch Block      | `try { ... } catch (Exception e) { ... }` | For exception handling                                      |
| Main Method          | `public static void main(String[] args)`  | Entry point of Java program                                 |
| Comments             | `// single line`, `/* multi-line */`      | Self-explanatory                                            |
|                      |                                           |                                                             |
### 🔹 **Array Syntax Table**

|**Operation**|**Syntax**|**Notes**|
|---|---|---|
|Declare Array|`int[] arr = new int[n];`|Default values are 0|
|Access Element|`arr[i]`|0-based index|
|Array Length|`arr.length`|Property, not method|
|Sort Array|`Arrays.sort(arr);`|Ascending order|
|Fill Array|`Arrays.fill(arr, val);`|All values become `val`|

---

### 🔹 **String Syntax Table**

|**Operation**|**Syntax**|**Notes**|
|---|---|---|
|Declare|`String s = "abc";`|Immutable|
|Length|`s.length();`|Returns int|
|Char at Index|`s.charAt(i);`|0-based indexing|
|Substring|`s.substring(i, j);`|i inclusive, j exclusive|
|Compare|`s.equals("abc")`|Use `.equals()` not `==`|
|Ignore Case Compare|`s.equalsIgnoreCase("ABC")`|Case-insensitive|
|Index of Substring|`s.indexOf("a");`|Returns -1 if not found|
|Split String|`s.split(" ");`|Returns `String[]`|
|Convert to CharArray|`s.toCharArray();`|For looping through characters|
|Convert int to String|`String.valueOf(x);`|Also works for other types|

---

### 🔹 **List (ArrayList) Syntax Table**

|**Operation**|**Syntax**|**Notes**|
|---|---|---|
|Declare List|`List<Integer> list = new ArrayList<>();`|Must use wrapper types|
|Add Element|`list.add(x);`|Appends at end|
|Get Element|`list.get(i);`|0-based indexing|
|Set Element|`list.set(i, val);`|Replace at index i|
|Remove by Index|`list.remove(i);`|Removes and shifts left|
|Check Contains|`list.contains(x);`|Returns boolean|
|Get Size|`list.size();`|Current number of elements|
|Sort|`Collections.sort(list);`|Ascending|
|Reverse|`Collections.reverse(list);`|In-place|

---

### 🔹 **HashMap Syntax Table**

| **Operation**    | **Syntax**                                    | **Notes**                    |
| ---------------- | --------------------------------------------- | ---------------------------- |
| Declare          | `Map<Integer, String> map = new HashMap<>();` | Generic types required       |
| Add/Update Entry | `map.put(key, val);`                          | Replaces if key exists       |
| Get Value        | `map.get(key);`                               | Returns null if key absent   |
| Check Key        | `map.containsKey(k);`                         | Returns boolean              |
| Check Value      | `map.containsValue(v);`                       | Slower, use when needed      |
| Remove Entry     | `map.remove(k);`                              | Removes key-value pair       |
| Size             | `map.size();`                                 | Number of entries            |
| Loop Entries     | `for (Map.Entry<K,V> e : map.entrySet())`     | `e.getKey()`, `e.getValue()` |

---

### 🔹 **HashSet Syntax Table**

|**Operation**|**Syntax**|**Notes**|
|---|---|---|
|Declare Set|`Set<Integer> set = new HashSet<>();`|Unique elements only|
|Add Element|`set.add(x);`|No duplicates|
|Check Contains|`set.contains(x);`|Fast lookup|
|Remove Element|`set.remove(x);`|No effect if not found|

---

### 🔹 **Stack Syntax Table**

|**Operation**|**Syntax**|**Notes**|
|---|---|---|
|Declare|`Stack<Integer> stack = new Stack<>();`|Last In First Out|
|Push|`stack.push(x);`|Add to top|
|Pop|`stack.pop();`|Removes top, returns value|
|Peek|`stack.peek();`|View top without removing|
|Check Empty|`stack.isEmpty();`|Returns boolean|

---

### 🔹 **Queue (LinkedList) Syntax Table**

|**Operation**|**Syntax**|**Notes**|
|---|---|---|
|Declare|`Queue<Integer> q = new LinkedList<>();`|FIFO|
|Offer/Add|`q.offer(x);`|Adds to back|
|Poll/Remove|`q.poll();`|Removes from front|
|Peek|`q.peek();`|View front|

---

### 🔹 **Deque Syntax Table**

|**Operation**|**Syntax**|**Notes**|
|---|---|---|
|Declare|`Deque<Integer> dq = new ArrayDeque<>();`|Double-ended queue|
|Add First/Last|`dq.addFirst(x);`, `dq.addLast(x);`||
|Remove First/Last|`dq.removeFirst();`, `dq.removeLast();`||

---

### 🔹 **PriorityQueue (Heap) Syntax Table**

|**Operation**|**Syntax**|**Notes**|
|---|---|---|
|Min-Heap|`PriorityQueue<Integer> pq = new PriorityQueue<>();`|Default behavior|
|Max-Heap|`PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());`|Reverse order for max heap|
|Add|`pq.add(x);`|Adds to heap|
|Remove Top|`pq.poll();`|Removes root|
|Peek Top|`pq.peek();`|View root|

---

### 🔹 **Math Functions Table**

|**Function**|**Syntax**|**Notes**|
|---|---|---|
|Max/Min|`Math.max(a, b);`|Returns greater/smaller|
|Absolute Value|`Math.abs(x);`|Negative to positive|
|Power|`Math.pow(a, b);`|a raised to b|
|Square Root|`Math.sqrt(x);`|Returns double|
|Floor/Ceil|`Math.floor(x);`, `Math.ceil(x);`|Round down/up|
|Random Number|`Math.random();`|Returns 0.0 – 1.0|

---

### 🔹 **Character Functions Table**

|**Function**|**Syntax**|**Notes**|
|---|---|---|
|Is Digit|`Character.isDigit(c);`|Checks if `c` is 0–9|
|Is Letter|`Character.isLetter(c);`|Checks if `c` is a-z or A-Z|
|To Lowercase|`Character.toLowerCase(c);`|Converts to lowercase|
|To Uppercase|`Character.toUpperCase(c);`|Converts to uppercase|

---

### 🔹 **Recursion Template**

```java
void recur(int i) {   if (i == n) return;   
	// do something   recur(i + 1); 
}
```

Use cases:

- Factorial
- Fibonacci
- DFS
- Permutations

---

### 🔹 **Backtracking Template**

```java
void backtrack(List<Integer> temp, boolean[] used, int[] nums) {   
	if (temp.size() == nums.length) {     
		res.add(new ArrayList<>(temp));     
		return;   
	}    
	for (int i = 0; i < nums.length; i++) {
	     if (used[i]) 
		     continue;      
		used[i] = true;     
		temp.add(nums[i]);     
		backtrack(temp, used, nums);     
		temp.remove(temp.size() - 1);     
		used[i] = false;   
} }
```

Use cases:

- Permutations / Combinations
- N-Queens
- Word Search
- Sudoku Solver

---

### 🔹 **Binary Search Template**

```java
int left = 0, 
right = arr.length - 1;  
while (left <= right) {   
	int mid = left + (right - left) / 2;    
	if (arr[mid] == target)     
		return mid;   
	else if (arr[mid] < target)     
		left = mid + 1;   
	else     
		right = mid - 1; 
	}
```

Use cases:

- Find in sorted array
- First/Last Occurrence
- Rotated Array
- Peak Element

---

### 🔹 **DFS Template (Graph)**

```java
void dfs(int node, boolean[] visited, List<List<Integer>> graph) {   
	visited[node] = true;    
	for (int neighbor : graph.get(node)) {     
		if (!visited[neighbor])       
		dfs(neighbor, visited, graph);   
	} 
}
```

Use cases:

- Connected Components
- Island Count
- Topological Sort (with stack)
- Cycle Detection

---

### 🔹 **BFS Template (Graph)**

```java
Queue<Integer> queue = new LinkedList<>(); queue.offer(start); visited[start] = true;  
while (!queue.isEmpty()) {   
	int node = queue.poll();    
	for (int neighbor : graph.get(node)) {     
		if (!visited[neighbor]) {       
			queue.offer(neighbor);       
			visited[neighbor] = true;     
		}   
	} 
}
```

Use cases:

- Shortest path (unweighted)
- Word Ladder
- Maze problems
- Bipartite Graph

---

### 🔹 **TreeNode Structure**

```java
class TreeNode {   
	int val;   
	TreeNode left, right;    
	TreeNode(int val) {     this.val = val;   } 
}
```

Use cases:

- Binary Tree Traversal
- BST operations
- Lowest Common Ancestor

---

### 🔹 **ListNode Structure**

```java
class ListNode {   
	int val;   
	ListNode next;    
	ListNode(int val) {     this.val = val;   } 
}
```

Use cases:

- Reverse Linked List
- Merge Sorted Lists
- Detect Cycle
- Palindrome Linked List

---

### 🔹 **Dynamic Programming Template (Top-Down with Memo)**

```java
int dp(int i, int[] memo) {   
	if (i <= 1) return i;   
		if (memo[i] != -1) 
			return memo[i];    
		return memo[i] = dp(i - 1, memo) + dp(i - 2, memo); 
}
```

### 🔹 **Dynamic Programming Template (Bottom-Up)**

```java
int[] dp = new int[n + 1]; 
dp[0] = 0; dp[1] = 1;  
for (int i = 2; i <= n; i++) {   
	dp[i] = dp[i - 1] + dp[i - 2]; 
}
```

Use cases:

- Fibonacci
- Knapsack
- Longest Increasing Subsequence
- Coin Change

---

### 🔹 **Custom Comparator for Sorting**

```java
Arrays.sort(arr, (a, b) -> {   
	// ascending: return a - b;   
	// descending: return b - a; });
```

For sorting custom objects:

```java
class Pair {   int x, y;   Pair(int x, int y) { 
	this.x = x; this.y = y; } }  
Arrays.sort(pairs, (a, b) -> {   
	if (a.x == b.x) return a.y - b.y;   
	return a.x - b.x; 
});
```