# Properties of Relation Matrices

##  Project Overview
This project generates and analyzes random relation matrices to determine key properties of relations such as symmetry, anti-symmetry, transitivity, equivalence, and functionality. The program creates symmetric binary matrices and checks these properties efficiently, outputting the results to a file.

This was developed as part of my **Discrete Mathematics (CSE 106)** course project at university.
This project generates random **relation matrices** and checks their key properties relevant to relations in discrete mathematics, including:

- Symmetry
- Anti-symmetry
- Transitivity
- Equivalence relation
- Function property

The program outputs these matrices and their property evaluations to a text file.

---

## 🧩 Problem Statement

Given an integer `n`, the program generates `n` symmetric random relation matrices of size `n x n`, where entries are either 0 or 1, with the diagonal fixed at 0 (no self-relations). It then determines whether each matrix satisfies important relation properties.

---
##  Features

- Generates random symmetric relation matrices.
- Checks for:
  - **Symmetry:** `R` is symmetric if for all `a,b`, `R(a,b) = R(b,a)`.
  - **Anti-symmetry:** `R` is anti-symmetric if no pair of distinct elements is mutually related.
  - **Transitivity:** If `(a,b)` and `(b,c)` are in `R`, then `(a,c)` is also in `R`.
  - **Equivalence Relation:** Relation is equivalence if it is symmetric and transitive.
  - **Function:** Each column contains at most one `1`, meaning a functional relation.
- Measures and records execution time for property checks.
- Outputs results to a file named `relations.txt`.

---

##  Theoretical Complexity Analysis

In the given code, the most significant operations are:

1. **Generating a random matrix**  
   - Time Complexity: **O(n²)**  
   - Uses nested loops to fill a symmetric matrix with random values.

2. **Checking symmetry**  
   - Time Complexity: **O(n²)**  
   - Compares each element with its symmetric counterpart across the diagonal.

3. **Checking anti-symmetry**  
   - Time Complexity: **O(n²)**  
   - Checks for mutually related pairs (except diagonal) to ensure they don’t exist.

4. **Checking transitivity**  
   - Time Complexity: **O(n³)**  
   - For each related pair `(a, b)` and `(b, c)`, it verifies whether `(a, c)` also exists.

5. **Checking equivalence**  
   - Time Complexity: **O(n² + n³) = O(n³)**  
   - Since it depends on both symmetry and transitivity checks.

6. **Checking function**  
   - Time Complexity: **O(n²)**  
   - Ensures each column has at most one '1', modeling a valid function.

### ⏱️ Overall Complexity
The total time complexity is **O(n³)**, dominated by the transitivity check.

---
## 📂 File Structure

- `CSE106.c` — C source code implementing relation matrix generation and property checks.
- `relations.txt` — Output file containing generated matrices and property results.

---

## ✅ Requirements

- Standard C compiler (GCC or compatible)
- Linux or Unix environment recommended (for `clock_gettime`)

---

## 🛠️ How It Works

- Prompts user for the number of relation matrices (`n`) to generate.
- Uses random number generator seeded by current time to create symmetric matrices.
- Iteratively tests matrices for the listed properties.
- Writes matrices and property results to a text file.
- Execution time is calculated using `clock_gettime` for performance insight.

---

##  Sample Input & Output
![image](https://github.com/user-attachments/assets/10538501-8a08-4853-9d3b-424e9f6b6fd2)

![image](https://github.com/user-attachments/assets/c7c4acc9-46ae-4154-99b6-c77dba5b00dd)



