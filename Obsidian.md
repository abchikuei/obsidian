# 📚 Notes
## 🏷️ Topics
| #   | Topic                    | Tag   |
| --- | ------------------------ | ----- |
| 1   | Software Engineering     | `#SE` |
| 2   | Computer Science         | `#CS` |
| 3   | Competitive Programming  | `#CP` |
| 4   | Mathematics Fundamentals | `#MF` |
| 5   | General Facts            | `#GF` |
|     |                          |       |

--- 
# Sunday April 12 2026 | #CP 

### 📝 **Overview**
A **Trie** is a tree-based data structure optimized for **prefix queries**. It is commonly used in **search engines**, **autocomplete**, and **spell checkers**.

This implementation supports 3 operations:

- **`insert(word)`** — add a word to the trie
- **`search(word)`** — check whether an **exact word** exists
- **`startsWith(prefix)`** — check whether any word starts with the given prefix

**Core idea:**
- Each node represents one character position.
- Children are stored in a fixed-size array of length `26`.
- Index mapping uses ASCII offsets: `'a' -> 0`, `'b' -> 1`, ..., `'z' -> 25`.
- `isEnd` marks whether a node terminates a valid word.

> [!NOTE]
> The **root node is dummy**: it does not store a character itself.


### 🛠️ **Implementation**
```typescript
class TrieNode {
	public children: (null | TrieNode)[];
	public isEnd: boolean;

	public constructor() {
		this.children = Array.from({ length: 26 }, () => null);
		this.isEnd = false;
	}
}

export class Trie {
	private root: TrieNode;

	public constructor() {
		this.root = new TrieNode(); // dummy node
	}

	public insert(word: string) {
		let current = this.root;

		for (let i = 0; i < word.length; i++) {
			const ascii = word.charCodeAt(i) - 97;
			if (!current.children[ascii]) {
				current.children[ascii] = new TrieNode();
			}
			current = current.children[ascii];
		}

		current.isEnd = true;
	}

	public search(word: string) {
		let current = this.root;

		for (let i = 0; i < word.length; i++) {
			const ascii = word.charCodeAt(i) - 97;
			if (!current.children[ascii]) return false;
			current = current.children[ascii];
		}

		return current.isEnd;
	}

	public startsWith(word: string) {
		let current = this.root;

		for (let i = 0; i < word.length; i++) {
			const ascii = word.charCodeAt(i) - 97;
			if (!current.children[ascii]) return false;
			current = current.children[ascii];
		}
		return true;
	}
}
```



### 📊 **Complexity**
| Operation | Time Complexity | Space Complexity |
|---|---:|---:|
| `insert(word)` | **O(L)** | **O(L)** |
| `search(word)` | **O(L)** | **O(1)** |
| `startsWith(prefix)` | **O(L)** | **O(1)** |

Where `L` is the length of the input string.

**Overall Trie storage:**  
- **Space Complexity:** **O(N · L)** in the worst case, where `N` is the number of inserted words and `L` is average word length.


### 💡 **Key Insights**
- **`search`** requires a full match: the traversal must end on a node with `isEnd = true`.
- **`startsWith`** only checks whether the path exists; it does **not** require `isEnd`.
- Using a fixed array of size `26` makes child lookup **O(1)**.
- This implementation assumes all input characters are **lowercase English letters**.

> [!WARNING]
> If the input may contain uppercase letters, symbols, or non-English characters, the `charCodeAt(i) - 97` mapping will break.


### 🔍 **Invariants / Details**
- Every node’s `children` array has exactly **26 slots**.
- A `null` entry means the corresponding child does **not** exist.
- `isEnd = true` means a complete word ends at that node.
- The trie does **not** store full strings; it stores only structural character paths.

**Traversal pattern:**
1. Start at `root`
2. Convert each character to an index
3. Follow or create the corresponding child
4. Mark the final node with `isEnd = true` for insertion


### 🧠 **Method Behavior Summary**
| Method       | Purpose           | Requires `isEnd`? |
| ------------ | ----------------- | ----------------: |
| `insert`     | Add a word        |                No |
| `search`     | Exact word lookup |               Yes |
| `startsWith` | Prefix lookup     |                No |

---
# Sunday April 12 2026 | #CP 

### 📝 **Overview**
Given `n` books, number them from `1` to `n` and count how many **digits** are written in total.

**Example (`n = 13`):**
- `1..9` → `9` digits
- `10..13` → `4 × 2 = 8` digits
- **Total** → `17`

> [!NOTE]
> Think of the numbers as **digit layers**:
> - 1st layer: all numbers `1..n`
> - 2nd layer: numbers `10..n`
> - 3rd layer: numbers `100..n`
> - and so on


### 🛠️ **Implementation**
```typescript
import * as fs from "fs";

const readInput = () => {
	const debug = process.env.DEBUG_FILE_INPUT;
	return fs.readFileSync(debug ?? 0, "utf-8");
};

const data = readInput();
const tokens = data.split(/\s+/g).filter(Boolean);
const lines = data.split(/\r?\n/);

let t = 0;
let l = 0;

const read = () => tokens[t++];
const int = () => Number(read());
const line = () => lines[l++];
const readline = () => line().trim().split(/\s+/g);

let out = "";
const write = (...s: any[]) => (out += s.join(" ") + "\n");
const flush = () => process.stdout.write(out);

/* 
Codeforces | 📚 Vanya and Books

📝 The Story (Simplified)

Vanya has $n$ books in a library. He needs to put a number on every book, starting from 1 all the way to $n$.
The Question: How many total digits (individual numbers like 0, 1, 2...) does he need to write?

Example: If there are 13 books:
- Books 1 to 9 use 9 digits.
- Books 10, 11, 12, 13 use 2 digits each ($4 \times 2 = 8$ digits).
- Total: $9 + 8 = 17$ digits.

---

Constraints:

1 <= n <= 10^9

---

The idea would be thinking digits as layers. Every number has at least 1 layer (the ones place), 
numbers 10 and above have a second layer (the tens place). Number above 100 have a third, and so on

Book:  1 2 3 4 5 6 7 8 9 10 11 12 13
Layer 1: * * * * * * * * * * * * * (13 stars)
Layer 2:                    * * * * ( 4 stars)
--------------------------------------
Total:                                 17 stars

---

Tip: We could have also used `String().length` instead of this

*/

function solve() {
	let n = int();
	let totalDigits = 0;

	for (let i = 1; i <= n; i *= 10) {
		totalDigits += n - i + 1;
	}

	write(totalDigits);
}

function main() {
	solve();
	flush();
}

main();
```


### 🔍 **Invariants / Details**
- For each power of ten `i = 1, 10, 100, ...`, count how many numbers have at least that many digits.
- The number of integers from `i` to `n` is `n - i + 1`.
- Summing these counts gives the total number of written digits.


### 💡 **Key Insights**
- This is a **counting by digit positions** trick, not a simulation.
- The loop runs only while `i <= n`, so it iterates about `log10(n)` times.
- A direct alternative is to convert each number to a string and sum `length`, but that is unnecessary here.

> [!NOTE]
> The formula works because every number contributes **one digit per active decimal layer**.


### 📊 **Complexity**
| Metric | Value |
|---|---:|
| ⏱️ **Time Complexity** | `O(log n)` |
| 💾 **Space Complexity** | `O(1)` |

### 🛠️ **Implementation Idea**
For each decimal layer:
- `1` → counts all numbers
- `10` → counts numbers with at least 2 digits
- `100` → counts numbers with at least 3 digits
- continue until `i > n`

This yields the total digit count in a compact loop.

> [!INFO]- Monday April 13 2026 | #MF
> **Formula series: Closed-form sums**

### Overview=
Closed-form formulas for common arithmetic series...

### 📝 **Overview**
Closed-form formulas for common arithmetic series. Useful for **math shortcuts**, **algorithm analysis**, and **competitive programming**.

### 🔍 **Invariants / Details**

> [!NOTE]
> In these formulas, `n` denotes the **count of terms**, not necessarily the last value in the sequence.

#### 1) Sum of first `n` natural numbers
$$
1 + 2 + 3 + \dots + n = \frac{n(n+1)}{2}
$$
#### 2) Sum of first `n` odd numbers
$$
1 + 3 + 5 + \dots + n = n^2
$$

#### 3) Sum of squares of first `n` natural numbers
$$
1^2 + 2^2 + 3^2 + \dots + n^2 = \frac{n(n+1)(2n+1)}{6}
$$

#### 4) Sum of squares of first `n` odd numbers
$$
1^2 + 3^2 + 5^2 + \dots + n^2 = \frac{n(4n^2-1)}{3}
$$

#### 5) Sum of squares of first `n` even numbers
$$
2^2 + 4^2 + 6^2 + \dots + n^2 = \frac{2n(n+1)(2n+1)}{3}
$$

#### 6) Sum of cubes of first `n` natural numbers
$$
1^3 + 2^3 + 3^3 + \dots + n^3 = \left(\frac{n(n+1)}{2}\right)^2
$$

#### 7) Sum of cubes of first `n` odd natural numbers
$$
1^3 + 3^3 + 5^3 + \dots + n^3 = n^2(2n^2-1)
$$

#### 8) Sum of cubes of first `n` even natural numbers
$$
2^3 + 4^3 + 6^3 + \dots + n^3 = 2n^2(n+1)^2
$$

---
# Monday April 13 2026 | #CP 

### 📝 Overview

**Goal:** Reorder an integer array `nums` in-place so that it satisfies the **wiggle pattern**:

- `nums[0] <= nums[1] >= nums[2] <= nums[3] >= nums[4] ...`

This is **not** full sorting; only local order constraints between neighbors matter.

**Example**

- Input: `[3, 5, 2, 1, 6, 4]`  
- Valid output: `[3, 5, 1, 6, 2, 4]`  
  - `3 <= 5 >= 1 <= 6 >= 2 <= 4` ✅

Constraints:

- `1 <= nums.length <= 50_000`
- `-10_000 <= nums[i] <= 10_000` (typical LeetCode-style; original note: “up to 10K”)

### 🛠️ Implementation

```typescript
export class Solution {
	/**
	 * Leetcode | Wiggle Sort
	 * Given an integer array and we have to sort in a way:
	 * nums[0] <= nums[1] and nums[1] >= nums[2] and nums[2] <= nums[3] etc.
	 *
	 * Array size up to 50K
	 * Array element up to 10K
	 *
	 * Input: [3,5,2,1,6,4]
	 * Output: [3,5,1,6,2,4]
	 *
	 * [3,5,1,6,2,4] - Sorted -> [1,2,3,4,5,6]
	 */
	wiggleSort = (nums: number[]): number[] => {
		// if we have empty or single element array
		if (nums.length < 2) return nums;

		for (let i = 1; i < nums.length; i++) {
			if (i & 1 && nums[i] < nums[i - 1]) {
				[nums[i], nums[i - 1]] = [nums[i - 1], nums[i]];
			}

			if (!(i & 1) && nums[i] > nums[i - 1]) {
				[nums[i], nums[i - 1]] = [nums[i - 1], nums[i]];
			}
		}

		return nums;
	};
}
```

### 📊 Complexity

| Aspect              | Complexity |
|---------------------|-----------:|
| ⏱️ **Time**         | `O(n)`     |
| 💾 **Space**        | `O(1)`     |
| ✅ **In-place**     | Yes        |
| 🔁 **Single pass**  | Yes        |

### 💡 Key Insights

- The algorithm enforces the **local wiggle condition** by scanning once and **swapping adjacent elements** only when the condition is violated.
- **Odd indices (`i & 1`):** must satisfy `nums[i - 1] <= nums[i]`.
- **Even indices (`!(i & 1)`):** must satisfy `nums[i - 1] >= nums[i]`.
- No global sort is needed; local fixes are sufficient to guarantee the entire array is in wiggle form.

> [!NOTE]
> This is **Wiggle Sort I** (local pattern only), not the harder version that requires a specific order relative to the median.

### 🔍 Invariants / Details

- **Loop invariant at index `i`:**
  - For all `k` in `[0, i]`, the wiggle property holds:
    - If `k` is even: `nums[k] <= nums[k + 1]` (when `k + 1` exists)
    - If `k` is odd:  `nums[k] >= nums[k + 1]` (when `k + 1` exists)

- **Bitwise check `i & 1`:**
  - `i & 1` is `1` for odd `i`, `0` for even `i`.
  - Used as a fast parity check to decide which inequality to enforce.

- **Swap logic:**
  - At odd `i`: if `nums[i] < nums[i - 1]`, swap → ensures `nums[i - 1] <= nums[i]`.
  - At even `i`: if `nums[i] > nums[i - 1]`, swap → ensures `nums[i - 1] >= nums[i]`.

This guarantees the wiggle pattern after a single left-to-right pass.


---
# Tuesday April 14 2026 | #CP

### 📝 Overview

Given an array of non-negative integers, arrange them to form the **largest possible number** (as a string).

Core idea:  
Sort numbers by a **custom comparator** that compares concatenated strings:  
- For `a` and `b`, compare `String(a) + String(b)` vs `String(b) + String(a)`  
- Order them so that the **larger concatenation** comes first.

### 🛠️ Implementation

```typescript
export const largestNumber = (nums: number[]): string => {
	nums.sort((a, b) =>
		String(a) + String(b) > String(b) + String(a) ? -1 : 1,
	);
	const joined = nums.join("");
	return joined[0] === "0" ? "0" : joined;
};

// 3 39

// 339 393

// The idea is comparing them as string
```

### 📊 Complexity

| Aspect              | Complexity      |
|---------------------|-----------------|
| ⏱️ **Time**         | O(n log n · k)  |
| 💾 **Space**        | O(k) extra      |

- `n` — number of elements in `nums`  
- `k` — max number of digits per number (string conversion & comparison cost)

### 💡 Key Insights

- **Comparator logic**:  
  - For `a = 3`, `b = 39`  
    - `String(a) + String(b) = "3" + "39" = "339"`  
    - `String(b) + String(a) = "39" + "3" = "393"`  
    - `"393" > "339"` ⇒ `39` should come **before** `3`.
- Final result is returned as a **string**, not a number, to avoid:
  - Leading zero stripping
  - Integer overflow for very large concatenations

### 🔍 Invariants / Details

- **Sorting invariant**:  
  For any pair `a`, `b` in the sorted array,  
  `String(a) + String(b) >= String(b) + String(a)`  
  holds in the final order.

- **All zeros edge case**:  
  If the array is like `[0, 0, 0]`, sorting yields `"000"`.  
  The check `joined[0] === "0" ? "0" : joined` ensures the result is `"0"` instead of `"000"`.

> [!NOTE]
> The comparator never returns `0` (ties are broken arbitrarily as `1`), but this is acceptable because equal concatenations (`ab == ba`) are interchangeable for the final result.



---
# Tuesday April 14 2026 | #CP 

### 📝 **Overview**
**Goal:** support three operations on a set in **average O(1)** time:

- `insert(val)` → add a value if it does not exist
- `remove(val)` → delete a value if it exists
- `getRandom()` → return a random element from the current set

**Core idea:** combine:
- **`Map<number, number>`** to store **value → index**
- **`number[]`** to store values in a compact array

This allows:
- fast existence checks via `Map`
- fast deletion by swapping the target with the last array element
- fast random access via array indexing

---

### 🛠️ **Implementation**
```typescript
// Leetcode | Insert, Delete, GetRandom in O(1)

export class RandomizedSet {
	private map: Map<number, number>; // value, index
	private array: number[];

	public constructor() {
		this.map = new Map();
		this.array = [];
	}

	public insert(inserting_value: number) {
		if (this.map.has(inserting_value)) return false;
		this.map.set(inserting_value, this.array.length);
		this.array.push(inserting_value);
		return true;
	}

	public remove(deleting_value: number) {
		if (!this.array.length) return false;

		const deleting_index = this.map.get(deleting_value);

		// strongly check for undefined otherwise 0 will fall for it
		if (deleting_index === undefined) return false;

		const last_index = this.array.length - 1;
		const last_value = this.array[last_index];

		if (last_index !== deleting_index) {
			[this.array[last_index], this.array[deleting_index]] = [
				this.array[deleting_index],
				this.array[last_index],
			];
		}

		this.map.set(last_value, deleting_index);

		this.array.pop();
		this.map.delete(deleting_value);

		return true;
	}
	public getRandom() {
		const random_index = Math.floor(Math.random() * this.array.length);
		return this.array[random_index];
	}
}
```

---

### 📊 **Complexity**

| Operation | Time Complexity | Space Complexity |
|---|---:|---:|
| `insert` | **O(1)** average | **O(1)** |
| `remove` | **O(1)** average | **O(1)** |
| `getRandom` | **O(1)** | **O(1)** |

**Overall space:** **O(n)** for storing all elements in the set.

---

### 💡 **Key Insights**
- **Array gives O(1) random access.**
- **Map gives O(1) lookup** for whether a value exists and where it is stored.
- **Deletion is the tricky part:** remove in O(1) by:
  1. finding the index of the element to delete
  2. swapping it with the last element
  3. popping the last element
  4. updating the moved element’s index in the map

> [!NOTE]
> The explicit check `deleting_index === undefined` is important.  
> Do **not** use a truthy check here, because index `0` is valid and would be treated as falsy.

---

### 🔍 **Invariants / Details**
- `map.get(value)` always stores the **current index** of `value` in `array`.
- `array` contains **all values exactly once**.
- After a swap during removal, the moved `last_value` must have its index updated in `map`.
- `getRandom()` assumes the set is **non-empty**; otherwise `Math.random() * 0` returns `0`, and indexing an empty array yields `undefined`.

> [!NOTE]
> This implementation provides **average O(1)** operations.  
> The randomness and hash map behavior are standard expected-case guarantees, not worst-case guarantees.

---

### 🛠️ **Removal Logic Summary**
1. Find `deleting_index` from `map`
2. Get `last_index` and `last_value`
3. If needed, swap target with last element
4. Update `last_value`’s index in `map`
5. `pop()` the array
6. Delete `deleting_value` from `map`

This is the standard pattern for **O(1) deletion from an array-backed set**.
