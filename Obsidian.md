**Topics**:

1. **Software Engineering** #SE
2. **Computer Science** #CS
3. **Competitive Programming** #CP
4. **Mathematic Fundamentals** #MF
5. **General Facts** #GF


--- 
## Sunday April 12 2026 | #CP

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

---

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

---

### 📊 **Complexity**
| Operation | Time Complexity | Space Complexity |
|---|---:|---:|
| `insert(word)` | **O(L)** | **O(L)** |
| `search(word)` | **O(L)** | **O(1)** |
| `startsWith(prefix)` | **O(L)** | **O(1)** |

Where `L` is the length of the input string.

**Overall Trie storage:**  
- **Space Complexity:** **O(N · L)** in the worst case, where `N` is the number of inserted words and `L` is average word length.

---

### 💡 **Key Insights**
- **`search`** requires a full match: the traversal must end on a node with `isEnd = true`.
- **`startsWith`** only checks whether the path exists; it does **not** require `isEnd`.
- Using a fixed array of size `26` makes child lookup **O(1)**.
- This implementation assumes all input characters are **lowercase English letters**.

> [!WARNING]
> If the input may contain uppercase letters, symbols, or non-English characters, the `charCodeAt(i) - 97` mapping will break.

---

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

---

### 🧠 **Method Behavior Summary**
| Method       | Purpose           | Requires `isEnd`? |
| ------------ | ----------------- | ----------------: |
| `insert`     | Add a word        |                No |
| `search`     | Exact word lookup |               Yes |
| `startsWith` | Prefix lookup     |                No |

---
## Sunday April 12 2026 | #CP 

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

---

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

---

### 🔍 **Invariants / Details**
- For each power of ten `i = 1, 10, 100, ...`, count how many numbers have at least that many digits.
- The number of integers from `i` to `n` is `n - i + 1`.
- Summing these counts gives the total number of written digits.

---

### 💡 **Key Insights**
- This is a **counting by digit positions** trick, not a simulation.
- The loop runs only while `i <= n`, so it iterates about `log10(n)` times.
- A direct alternative is to convert each number to a string and sum `length`, but that is unnecessary here.

> [!NOTE]
> The formula works because every number contributes **one digit per active decimal layer**.

---

### 📊 **Complexity**
| Metric | Value |
|---|---:|
| ⏱️ **Time Complexity** | `O(log n)` |
| 💾 **Space Complexity** | `O(1)` |

---

### 🛠️ **Implementation Idea**
For each decimal layer:
- `1` → counts all numbers
- `10` → counts numbers with at least 2 digits
- `100` → counts numbers with at least 3 digits
- continue until `i > n`

This yields the total digit count in a compact loop.
