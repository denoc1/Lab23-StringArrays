# Lab23-StringArrays
## Modifying arrays and returning arrays 

### Overview

In this lab, you will practice two important patterns in AP CSA:

1. Creating a **new array** inside a method and returning it
2. **Modifying an existing array** passed as a parameter (in-place)

This lab has **Core Methods (Required)** and **Optional Extension Methods**.

---

## Rules & Assumptions

* All arrays are **non-null** and contain **at least one element**
* Preserve the **original order** of elements when creating new arrays or modifying arrays

---

## Part A: Core Methods (Required for All Students)

### 1. `lengthArray`

```java
public static int[] lengthArray(String[] arr)
```

Creates a **new array** of integers representing the length of each string in `arr`.

**Sample Input / Output:**

| Input Array                 | Output Array |
| --------------------------- | ------------ |
| `["cat", "elephant", "hi"]` | `[3, 8, 2]`  |
| `["AP", "CSA"]`             | `[2, 3]`     |

---

### 2. `truncateWords`

```java
public static void truncateWords(String[] arr, int length)
```

**Modifies the array in-place**:

* For each string longer than `length`, truncate it to that length using `substring`
* Strings shorter than or equal to `length` remain unchanged

**Sample Input / Output:**

| Input Array                       |  length   | Result Array (after method) |
| --------------------------------- | --------- | --------------------------- |
| `["computer", "math", "science"]` | `5`       | `["compu", "math", "scien"]`  |
| `["java", "code"]`                | `3`      | `["jav", "cod"]`             |

> **Note:** This method demonstrates that arrays are passed by reference; changes made inside the method affect the original array.

---

## Part B: Optional Methods (For Students Who Finish Early)

### 3. `wordsLongerThan`

```java
public static String[] wordsLongerThan(String[] arr, int minLength)
```

Returns a **new array** containing exactly the strings in `arr` with length greater than `minLength`.  (Note - how do you determine the size of the new array?)

**Sample Input / Output:**

| Input Array                 | minLength | Output Array         |
| --------------------------- | --------- | -------------------- |
| `["cat", "elephant", "hi"]` | `3`       | `["elephant"]`       |
| `["one", "three", "seven"]` | `4`       | `["three", "seven"]` |

---

### 4. `countStartsWith`

```java
public static int countStartsWith(String[] arr, String prefix)
```

Returns the number of strings in `arr` that start with `prefix`.

**Sample Input / Output:**

| Input Array                           | Prefix | Return Value |
| ------------------------------------- | ------ | ------------ |
| `["apple", "banana", "apply", "ape"]` | `"ap"` | `3`          |
| `["dog", "cat", "cow"]`               | `"c"`  | `2`          |

---

### 5. `wordsThatStartWith`

```java
public static String[] wordsThatStartWith(String[] arr, String prefix)
```

Returns a **new array** containing only the strings that start with `prefix`, preserving the original order.

**Sample Input / Output:**

| Input Array                           | Prefix | Output Array                |
| ------------------------------------- | ------ | --------------------------- |
| `["apple", "banana", "apply", "ape"]` | `"ap"` | `["apple", "apply", "ape"]` |
| `["dog", "cat", "cow"]`               | `"c"`  | `["cat", "cow"]`            |

---
### 6. `swapFirstAndLastContaining` (Extra Challenging)
**Note:** This method is **optional** and intended for students looking for a challenge!
(There is a hint at the end of the document - only look if you want a hint...)

```java
public static void swapFirstAndLastContaining(String[] arr, String sub)
```

**Description:**

* Finds the **first word** in `arr` that contains the substring `sub`.
* Finds the **last word** in `arr` that contains `sub`.
* If both exist and are at **different positions**, swaps them **in-place**.
* If fewer than 2 words contain `sub`, the array remains unchanged.

**Sample Input / Output:**

| Input Array                                           | Substring | Result Array (after method)                           | Notes                                         |
| ----------------------------------------------------- | --------- | ----------------------------------------------------- | --------------------------------------------- |
| `["dog", "cat", "banana", "taco", "apple", "indigo"]` | `"a"`     | `["dog", "apple", "banana", "taco", "cat", "indigo"]` | Swap first (`cat`) and last (`apple`)         |
| `["dog", "fish", "moose"]`                            | `"m"`     | `["dog", "fish", "moose"]`                            | Only one word contains `"m"`, array unchanged |
| `["apple", "ape", "apply"]`                           | `"ap"`    | `["apply", "ape", "apple"]`                           | Swap first (`apple`) and last (`apply`)       |


---

## Notes

* Part A methods focus on **creating a new array** (`lengthArray`) and **modifying an array in-place** (`truncateWords`)
* Part B methods may require **counting first** to create a new array of correct size

* Test your methods using different arrays with different possible outcomes.  Push the boundaries!




## Hints for #6: Only read this if you want a hint!!



* Use **variables to track the first and last indices** containing the substring.
* Loop through the array **once** to identify these indices.
* Only perform the swap if **both indices are valid** and **different**.
* Remember: swapping elements requires a **temporary variable**.
