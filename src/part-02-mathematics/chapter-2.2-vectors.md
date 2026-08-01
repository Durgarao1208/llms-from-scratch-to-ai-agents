# 2.2 Vectors

## Learning Objectives

By the end of this chapter, you should be able to:

* Understand what a vector is.
* Explain the difference between scalars and vectors.
* Understand vector notation.
* Perform basic vector operations.
* Understand vector dimensions.
* Explain why embeddings are vectors.
* Understand how modern AI systems represent information using vectors.
* Build intuition for semantic meaning in vector spaces.

---

## Prerequisites

Before reading this chapter, you should understand:

* Scalars
* Basic arithmetic
* Neural network fundamentals

Refer to Chapter 2.1 if needed.

---

## Motivation

In the previous chapter, we learned about scalars.

Examples:

```text
30
67.4
0.95
```

Each scalar contains exactly one value.

But what if we need to describe something more complex?

For example:

A person's profile:

```text
Age = 30
Height = 166
Weight = 67.4
```

This is no longer a single value.

We need multiple values together.

Mathematics provides a structure for this:

> A vector.

---

## What Is a Vector?

A vector is an ordered collection of numbers.

Example:

```text
[30, 166, 67.4]
```

This vector contains three values.

Unlike a scalar:

```text
30
```

a vector can represent multiple pieces of information simultaneously.

---

## Scalar vs Vector

Scalar:

```text
30
```

Vector:

```text
[30, 166, 67.4]
```

Comparison:

| Property   | Scalar | Vector          |
| ---------- | ------ | --------------- |
| Values     | One    | Many            |
| Example    | 30     | [30, 166, 67.4] |
| Complexity | Simple | More expressive |

Vectors allow us to represent richer information.

---

## Why Vectors Matter in AI

Modern AI systems rarely work directly with words, images, or audio.

Instead, they convert everything into vectors.

Examples:

```text
Word
 ↓
Vector
```

```text
Image
 ↓
Vector
```

```text
Audio
 ↓
Vector
```

AI models operate primarily on vectors.

---

## Vector Notation

Vectors are typically written as:

```text
[1, 2, 3]
```

or

```text
(1, 2, 3)
```

In AI literature, vectors are often represented using bold symbols:

```text
v = [1, 2, 3]
```

For this book, we will use bracket notation.

---

## Understanding Dimensions

The number of values in a vector is called its dimension.

Example:

```text
[5]
```

Dimension:

```text
1
```

---

Example:

```text
[5, 10]
```

Dimension:

```text
2
```

---

Example:

```text
[5, 10, 15]
```

Dimension:

```text
3
```

---

Example:

```text
[1, 2, 3, 4, 5]
```

Dimension:

```text
5
```

The dimension equals the number of elements.

---

## Examples from Daily Life

Location on a map:

```text
[Latitude, Longitude]
```

Example:

```text
[17.6868, 83.2185]
```

This is a 2-dimensional vector.

---

RGB color:

```text
[Red, Green, Blue]
```

Example:

```text
[255, 100, 50]
```

This is a 3-dimensional vector.

---

Student profile:

```text
[Age, Height, Weight, Score]
```

Example:

```text
[20, 170, 65, 95]
```

This is a 4-dimensional vector.

---

## Vector Components

Consider:

```text
[10, 20, 30]
```

The components are:

```text
10
20
30
```

Each component is a scalar.

Therefore:

> A vector is a collection of scalars.

---

## Vectors in Programming

Java example:

```java
double[] vector = {10, 20, 30};
```

Another example:

```java
double[] embedding = {
    0.25,
    -0.81,
    1.24,
    0.67
};
```

This is a vector.

---

## Vector Addition

Consider:

```text
A = [1, 2, 3]

B = [4, 5, 6]
```

Addition occurs element by element.

```text
A + B

=
[1+4, 2+5, 3+6]

=
[5, 7, 9]
```

---

## Vector Subtraction

Example:

```text
A = [10, 20, 30]

B = [1, 2, 3]
```

Result:

```text
[9, 18, 27]
```

Subtraction also occurs element by element.

---

## Scalar Multiplication

Suppose:

```text
V = [1, 2, 3]
```

Multiply by 2:

```text
2 × V

=
[2, 4, 6]
```

Each element is multiplied by the scalar.

---

## Why These Operations Matter

Neural networks continuously perform:

* Vector addition
* Vector multiplication
* Scalar multiplication

These operations occur billions of times during training.

---

## Understanding Vectors Geometrically

Consider:

```text
[3, 4]
```

This can be interpreted as:

```text
Move 3 units horizontally
Move 4 units vertically
```

Vectors can represent both data and movement.

This geometric interpretation becomes useful later.

---

## Similarity Between Vectors

One of the most important ideas in AI is similarity.

Consider:

```text
Dog
```

and

```text
Puppy
```

Humans know these words are related.

Can a machine know this?

Yes.

Using vectors.

---

## Semantic Meaning

Modern AI systems represent words as vectors.

Example:

```text
Dog

=
[0.12, 0.88, -0.44, ...]
```

Puppy:

```text
[0.10, 0.90, -0.41, ...]
```

These vectors become similar.

As a result:

```text
Similar Meaning
     ↓
Similar Vectors
```

This is a foundational concept behind embeddings.

---

## Why Embeddings Are Vectors

An embedding is simply a vector representation of information.

Examples:

```text
Word Embedding
Sentence Embedding
Document Embedding
Image Embedding
```

All of these are vectors.

Example:

```text
[0.24, -0.13, 0.67, 1.21]
```

The vector captures meaning.

---

## Dimensions in Modern AI

Typical embedding sizes:

| Model        | Dimensions |
| ------------ | ---------- |
| Small Model  | 128        |
| Medium Model | 512        |
| Transformer  | 768        |
| Large LLM    | 4096+      |

A single word may be represented by thousands of numbers.

Each number is a scalar.

Together they form a vector.

---

## A Language Example

Consider the words:

```text
King
Queen
Man
Woman
```

Embeddings often capture relationships.

Example:

```text
King - Man + Woman
≈ Queen
```

This amazed researchers when first discovered.

The model learned semantic relationships automatically.

---

## Vectors in Neural Networks

A neural network rarely receives individual scalars.

Instead it receives vectors.

Example:

```text
Input Features

=
[Age, Income, Credit Score]
```

The network processes this vector.

Most AI systems operate primarily on vectors.

---

## Vectors in Large Language Models

Consider:

```text
Artificial Intelligence
```

The LLM first converts words into tokens.

Then:

```text
Tokens
  ↓
Embeddings
  ↓
Vectors
```

The model processes vectors rather than words.

This is one of the most important ideas in modern AI.

---

## A Building Block Analogy

Recall our hierarchy:

```text
Scalars
   ↓
Vectors
   ↓
Matrices
   ↓
Tensors
   ↓
Neural Networks
   ↓
Transformers
   ↓
LLMs
```

Vectors are the next layer above scalars.

---

## Common Misconceptions

### Misconception 1

Vectors are only arrows from school mathematics.

Reality:

In AI, vectors primarily represent information.

---

### Misconception 2

Vectors must have only two or three values.

Reality:

Modern AI vectors often contain thousands of values.

---

### Misconception 3

Embeddings are different from vectors.

Reality:

Embeddings are vectors.

---

## Enterprise Applications

Vectors are used throughout modern AI:

* Search systems
* Recommendation engines
* Fraud detection
* Semantic search
* Retrieval-Augmented Generation (RAG)
* Chatbots
* Large Language Models

Many modern AI products are fundamentally vector-processing systems.

---

## Key Takeaways

* A vector is an ordered collection of numbers.
* Vectors consist of scalars.
* The number of elements defines the dimension.
* Vectors support addition, subtraction, and scalar multiplication.
* Embeddings are vectors.
* Modern AI represents information using vectors.
* Similar meanings often produce similar vectors.
* LLMs operate heavily on vector representations.

---

## Interview Questions

### Beginner

1. What is a vector?
2. How does a vector differ from a scalar?
3. What is vector dimension?

### Intermediate

4. Explain vector addition.
5. Why are embeddings represented as vectors?
6. How are vectors used in neural networks?

### Advanced

7. Why do LLMs use vector representations?
8. How do vectors capture semantic meaning?
9. Why are high-dimensional vectors useful?

---

## Exercises

1. Create five example vectors from daily life.
2. Perform vector addition and subtraction manually.
3. Write a Java program representing vectors using arrays.
4. Research common embedding dimensions.
5. Explain why similar words should have similar vectors.

---

## Chapter Summary

Vectors are ordered collections of numbers that allow AI systems to represent complex information.

Embeddings, neural network inputs, and language representations are all built upon vectors.

Modern AI systems transform words, images, and other data into vectors because vectors make mathematical learning possible.

Understanding vectors is essential for understanding embeddings, attention mechanisms, transformers, and Large Language Models.

---

## Preview of Chapter 2.3

In the next chapter, we will study matrices.

We will learn:

* What matrices are
* Matrix dimensions
* Matrix operations
* Matrix multiplication
* Why neural networks rely on matrices
* How transformers perform massive matrix computations
* Why GPUs are optimized for matrix operations

Matrices are where AI mathematics starts becoming truly powerful.
