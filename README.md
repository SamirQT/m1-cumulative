# Part 1: Sequence & List Operations (8 Functions)

For each function:

1. A **Google‑style docstring** (`Args:`, `Returns:`, `Raises:`)
2. A few lines of **pseudocode** comments under the `def`
3. An **implementation** using only loops, conditionals, and built‑ins (no comprehensions, dicts, classes, or custom exceptions)
4. **Tests** in a central `main()` function (see Submission Checklist)

---

### 1. `print_even_indices(seq)`

Prints each element at even indices of a **string** or **list**:

```text
Index 0: <element>
Index 2: <element>
…
```

* Must handle `""` or `[]` without error.

---

### 2. `double_positives(nums)`

Modifies the **list** `nums` in place, doubling every positive integer; zeros and negatives unchanged.

* Verify aliasing: if you do `alias = nums` before calling, both names reflect updates.

---

### 3. `extract_vowels(s)`

Prints each vowel (`a, e, i, o, u`, any case) in **string** `s`, with its index:

```text
Index 1: e
Index 4: o
…
```

* If no vowels, prints nothing.
* Let Python’s `TypeError` surface if `s` isn’t a string.

---

### 4. `get_last_n(seq, n)`

Returns a **new list** containing the last `n` items of **string** or **list** `seq`.

* If `n < 0` or `n > len(seq)`, raise `ValueError("n out of range")`.
* Always return a `list`, even if `seq` is a string.

---

### 5. `count_occurrences(seq, item)`

Returns the number of times `item` appears in **string** or **list** `seq`.

* Compare via `==`, count manually in a loop.

---

### 6. `sum_list(nums)`

Returns the sum of all integers in **list** `nums`.

* Implement via a loop (no `sum()` builtin).
* If `nums` is empty, return `0`.

---

### 7. `average_list(nums)`

Returns the arithmetic mean of integers in **list** `nums`.

* Use your `sum_list(nums)` internally.
* If `nums` is empty, raise `ValueError("Cannot average empty list")`.

---

### 8. `unique_preserve_order(nums)`

Takes a **list** `nums` and returns a **new list** of its elements with duplicates removed in first‑occurrence order.

* E.g. `[2,3,2,1,3] → [2,3,1]`.
* Do **not** use dicts or comprehensions.

---

# Part 2: Exception Handling (4 Routines)

Same format: docstring, pseudocode, implementation, and tests in `main()`.

---

### 9. `inner(x)` & `outer(x)` (Raise Deep & Catch High)

* `inner(x)` raises `ValueError("Negative input")` if `x < 0`.
* `outer(x)` calls `inner(x)` inside `try`/`except`, catches **only** that `ValueError`, and prints:

  ```text
  Caught in outer: Negative input
  ```
* For `x >= 0`, `outer(x)` prints nothing.

---

### 10. `outer_chained(x)` (Error Chaining)

* Reuse the same `inner(x)`.
* In `outer_chained(x)`, catch `ValueError` as `e` and then:

  ```python
  raise RuntimeError("Processing failed") from e
  ```
* Running `outer_chained(-5)` uncaught should display a **chained traceback** showing both the `RuntimeError` and its original `ValueError`.

---

### 11. `safe_divide_list(nums, divisor)`

Returns a **new list** where each integer in `nums` is divided by `divisor`.

* If `divisor == 0`, catch `ZeroDivisionError` and instead raise `ValueError("Divisor must be non-zero")`.
* If any element of `nums` isn’t an integer, let Python’s `TypeError` bubble up.

---

### 12. `parse_and_sum(str_list)`

Given a **list of strings**, attempts to convert each to `int`.

* On successful conversion, add to a running total.
* On `ValueError`, catch it, print:

  ```text
  Warning: could not parse "<item>"
  ```

  and skip it.
* Return the final total.

---

# Submission Checklist

* **Module‑level docstring** at the very top of your `.py` file describing the assignment.
* **Twelve** definitions (`print_even_indices` through `parse_and_sum`), each with:

  * Google‑style **docstring**
  * **Pseudocode** comments
  * **Implementation** (no comprehensions, dicts, classes, or custom exceptions)
* A **`main()`** function that:

  * Calls **each** function **three times** with a variety of valid, edge‑case, and invalid inputs.
  * For **return‑value** functions, call and include an inline comment showing the expected return value.
  * For **print‑only** functions, call and include an inline comment showing the expected console output.
* At the very end of the file, simply:

  ```python
  main()
  ```
* An **“Exceptions Summary”** comment block below `main()` listing every built‑in exception your code may raise (`ValueError`, `RuntimeError`, `TypeError`, etc.) and the inputs that trigger them.

