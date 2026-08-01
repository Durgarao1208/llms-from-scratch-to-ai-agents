# 2.3 Matrices

## Learning Objectives

By the end of this chapter, you should be able to:

* Understand what a matrix is.
* Explain the relationship between scalars, vectors, and matrices.
* Understand matrix dimensions.
* Perform basic matrix operations.
* Understand matrix multiplication conceptually.
* Explain why neural networks rely heavily on matrices.
* Understand why GPUs excel at AI workloads.
* Recognize matrices inside embeddings, attention, and transformers.

---

## Prerequisites

Before reading this chapter, you should understand:

* Scalars
* Vectors
* Basic arithmetic

Refer to Chapters 2.1 and 2.2 if needed.

---

## Motivation

In the previous chapter, we learned that a vector is a collection of numbers.

Example:

```text
[10, 20, 30]
```

But what if we need to store multiple vectors together?

Consider a classroom:

| Student | Math | Science | English |
| ------- | ---- | ------- | ------- |
| A       | 80   | 90      | 85      |
| B       | 75   | 88      | 92      |
| C       | 95   | 91      | 89      |

This information is naturally arranged in rows and columns.

Mathematics provides a structure for this:

> A matrix.

---

## What Is a Matrix?

A matrix is a rectangular arrangement of numbers organized into rows and columns.

Example:

```text
[
 [1, 2, 3],
 [4, 5, 6],
 [7, 8, 9]
]
```

This is a matrix.

---

## From Scalars to Matrices

Recall our hierarchy:

Scalar:

```text
5
```

Vector:

```text
[1, 2, 3]
```

Matrix:

```text
[
 [1, 2, 3],
 [4, 5, 6]
]
```

Hierarchy:

```text
Scalar
   ↓
Vector
   ↓
Matrix
```

A matrix can be thought of as a collection of vectors.

---

## Understanding Rows and Columns

Consider:

```text
[
 [10, 20, 30],
 [40, 50, 60]
]
```

Rows:

```text
[10, 20, 30]

[40, 50, 60]
```

Columns:

```text
[10, 40]

[20, 50]

[30, 60]
```

Understanding rows and columns is essential for AI mathematics.

---

## Matrix Dimensions

Matrix dimensions are written as:

```text
Rows × Columns
```

Example:

```text
[
 [1, 2, 3],
 [4, 5, 6]
]
```

Rows:

```text
2
```

Columns:

```text
3
```

Dimension:

```text
2 × 3
```

---

## More Examples

Example 1:

```text
[
 [1, 2],
 [3, 4]
]
```

Dimension:

```text
2 × 2
```

---

Example 2:

```text
[
 [1, 2, 3],
 [4, 5, 6],
 [7, 8, 9]
]
```

Dimension:

```text
3 × 3
```

---

Example 3:

```text
[
 [5],
 [8],
 [9]
]
```

Dimension:

```text
3 × 1
```

---

## Real-World Analogy

Imagine a spreadsheet.

Example:

| Employee | Salary | Bonus |
| -------- | ------ | ----- |
| A        | 50000  | 5000  |
| B        | 60000  | 6000  |
| C        | 70000  | 7000  |

Ignoring labels:

```text
[
 [50000, 5000],
 [60000, 6000],
 [70000, 7000]
]
```

This is a matrix.

Matrices are essentially mathematical spreadsheets.

---

## Matrix Addition

Matrices can be added when dimensions match.

Example:

Matrix A:

```text
[
 [1, 2],
 [3, 4]
]
```

Matrix B:

```text
[
 [5, 6],
 [7, 8]
]
```

Result:

```text
[
 [6, 8],
 [10, 12]
]
```

Addition occurs element by element.

---

## Matrix Subtraction

Example:

```text
[
 [10, 20],
 [30, 40]
]
```

minus

```text
[
 [1, 2],
 [3, 4]
]
```

Result:

```text
[
 [9, 18],
 [27, 36]
]
```

Again, element-by-element.

---

## Scalar Multiplication

Multiply:

```text
[
 [1, 2],
 [3, 4]
]
```

by:

```text
2
```

Result:

```text
[
 [2, 4],
 [6, 8]
]
```

Every element is multiplied by the scalar.

---

## Why Matrix Multiplication Matters

Matrix multiplication is one of the most important operations in AI.

Nearly every neural network relies on it.

Nearly every transformer relies on it.

Nearly every LLM relies on it.

---

## Understanding Matrix Multiplication Intuitively

Consider:

```text
Input Features
      ↓
Neural Network
      ↓
Prediction
```

The neural network transforms inputs into outputs.

That transformation is largely achieved using matrix multiplication.

---

## A Neural Network Example

Suppose we have:

```text
Input Vector

[Age, Salary]
```

Example:

```text
[30, 100000]
```

The network contains learned weights.

Example:

```text
[
 [0.2, 0.8],
 [0.6, 0.1]
]
```

The network combines inputs and weights using matrix multiplication.

The result becomes the next layer's input.

---

## Why Neural Networks Love Matrices

Recall from Deep Learning:

```text
Input Layer
     ↓
Hidden Layer
     ↓
Output Layer
```

Each connection has a weight.

When represented mathematically:

```text
Inputs
   ×
Weights
   ↓
Outputs
```

This becomes matrix multiplication.

---

## Matrix Representation of Weights

Suppose:

```text
3 Inputs
4 Hidden Neurons
```

The weights can be stored as:

```text
3 × 4 Matrix
```

Example:

```text
[
 [0.1, 0.5, 0.8, 0.2],
 [0.3, 0.7, 0.4, 0.9],
 [0.6, 0.2, 0.1, 0.5]
]
```

Training adjusts these numbers.

---

## Why GPUs Are Important

Matrix operations require enormous computation.

Modern AI models perform:

```text
Millions
Billions
Trillions
```

of matrix operations.

GPUs are designed to execute many calculations simultaneously.

This makes them ideal for Deep Learning.

---

## Matrix Operations in Transformers

Transformers rely heavily on matrices.

For example:

```text
Input Embeddings
        ↓
Matrix Operations
        ↓
Attention Scores
        ↓
Matrix Operations
        ↓
Predictions
```

The majority of transformer computation involves matrices.

---

## Embeddings as Matrices

Suppose we have four words:

```text
Dog
Cat
Bird
Fish
```

Each word has a vector representation.

Example:

```text
Dog  = [0.1, 0.2, 0.3]

Cat  = [0.2, 0.1, 0.4]

Bird = [0.8, 0.4, 0.1]

Fish = [0.6, 0.5, 0.2]
```

Combined:

```text
[
 [0.1, 0.2, 0.3],
 [0.2, 0.1, 0.4],
 [0.8, 0.4, 0.1],
 [0.6, 0.5, 0.2]
]
```

This is an embedding matrix.

---

## Matrices Inside LLMs

When an LLM processes a sentence:

```text
I love AI
```

the words become vectors.

Those vectors become matrices.

The model then performs matrix operations repeatedly.

Even GPT models ultimately rely on large matrix computations.

---

## Why Matrix Multiplication Is Everywhere

Machine Learning:

```text
Features × Weights
```

Neural Networks:

```text
Inputs × Weight Matrices
```

Embeddings:

```text
Token IDs × Embedding Matrix
```

Attention:

```text
Queries × Keys
```

Transformers:

```text
Matrix × Matrix
```

LLMs:

```text
Billions of Matrix Operations
```

Matrix multiplication is one of the most important operations in AI.

---

## Common Misconceptions

### Misconception 1

Matrices are just large tables.

Reality:

Matrices represent transformations and computations.

---

### Misconception 2

Matrix multiplication is only a mathematical exercise.

Reality:

Modern AI depends heavily on matrix multiplication.

---

### Misconception 3

GPUs are important because they are fast.

Reality:

GPUs are important because they can perform many matrix operations in parallel.

---

## Enterprise Applications

Matrices appear in:

* Neural networks
* Recommendation systems
* Computer vision
* NLP systems
* Search engines
* RAG systems
* Fraud detection
* Large Language Models

Every modern AI system relies heavily on matrices.

---

## Key Takeaways

* A matrix is a collection of numbers arranged in rows and columns.
* Matrix dimensions are expressed as rows × columns.
* Matrices support addition, subtraction, and scalar multiplication.
* Matrix multiplication is fundamental to AI.
* Neural network weights are stored as matrices.
* Embeddings are often stored in matrices.
* Transformers perform large numbers of matrix operations.
* GPUs are optimized for matrix computations.

---

## Interview Questions

### Beginner

1. What is a matrix?
2. How is a matrix different from a vector?
3. How do you determine matrix dimensions?

### Intermediate

4. Why do neural networks use matrices?
5. What is matrix multiplication?
6. Why are GPUs useful for AI?

### Advanced

7. How are embeddings stored in matrices?
8. Why do transformers rely heavily on matrix operations?
9. Explain the role of matrices inside LLMs.

---

## Exercises

1. Create three matrices and identify their dimensions.
2. Perform matrix addition manually.
3. Perform scalar multiplication on a matrix.
4. Represent a classroom score sheet as a matrix.
5. Research GPU architectures optimized for matrix operations.

---

## Chapter Summary

Matrices extend vectors by organizing numbers into rows and columns.

They are one of the most important mathematical structures in AI because they enable efficient transformations and computations.

Neural networks, embeddings, transformers, and Large Language Models all depend heavily on matrix operations.

Understanding matrices is essential before moving to tensors, which form the foundation of modern deep learning frameworks.

---

## Preview of Chapter 2.4

In the next chapter, we will study tensors.

We will learn:

* What tensors are
* Why tensors generalize scalars, vectors, and matrices
* Tensor dimensions and ranks
* Tensor operations
* Why PyTorch and TensorFlow use tensors
* How transformers and LLMs represent data using tensors

Tensors are the final mathematical building block before we begin exploring neural network internals in depth.
