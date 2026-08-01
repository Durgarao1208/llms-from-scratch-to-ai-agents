# 2.4 Tensors

## Learning Objectives

By the end of this chapter, you should be able to:

* Understand what a tensor is.
* Explain the relationship between scalars, vectors, matrices, and tensors.
* Understand tensor dimensions and rank.
* Recognize tensors in Deep Learning frameworks.
* Understand why tensors are the fundamental data structure of AI.
* Explain how tensors are used in neural networks and transformers.
* Build intuition for tensors without requiring advanced mathematics.

---

## Prerequisites

Before reading this chapter, you should understand:

* Scalars
* Vectors
* Matrices

Refer to Chapters 2.1–2.3 if needed.

---

## Motivation

So far we have learned:

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

But modern AI systems process much more complex information.

Examples:

* Thousands of words
* Millions of images
* Hours of audio
* Videos containing thousands of frames

How do we represent such complex data?

The answer is:

> Tensors.

---

## What Is a Tensor?

A tensor is a mathematical structure that generalizes:

* Scalars
* Vectors
* Matrices

A tensor can have any number of dimensions.

Think of tensors as containers for numbers.

The simplest way to understand tensors is through hierarchy.

---

## The Tensor Hierarchy

### Rank 0 Tensor

A scalar:

```text
5
```

---

### Rank 1 Tensor

A vector:

```text
[1, 2, 3]
```

---

### Rank 2 Tensor

A matrix:

```text
[
 [1, 2, 3],
 [4, 5, 6]
]
```

---

### Rank 3 Tensor

A collection of matrices:

```text
[
  Matrix 1,
  Matrix 2,
  Matrix 3
]
```

---

### Rank 4 Tensor

A collection of rank-3 tensors.

And so on.

---

## Why AI Uses Tensors

Modern AI processes large amounts of structured data.

Examples:

### Image Classification

A single image:

```text
Height × Width × Channels
```

Example:

```text
224 × 224 × 3
```

This is naturally represented as a tensor.

---

### Video Processing

Video consists of:

```text
Frames × Height × Width × Channels
```

Example:

```text
100 × 224 × 224 × 3
```

This is a higher-dimensional tensor.

---

### Language Models

Transformers process:

```text
Batch × Tokens × Embedding Dimensions
```

Example:

```text
32 × 512 × 768
```

Again:

A tensor.

---

## Understanding Dimensions

Consider:

```text
[1, 2, 3]
```

Shape:

```text
(3)
```

---

Consider:

```text
[
 [1, 2, 3],
 [4, 5, 6]
]
```

Shape:

```text
(2, 3)
```

Meaning:

```text
2 rows
3 columns
```

---

Tensor shapes simply describe dimensions.

---

## What Is Shape?

Shape tells us how data is organized.

Example:

```text
(3)
```

Three values.

---

Example:

```text
(2, 3)
```

Two rows and three columns.

---

Example:

```text
(32, 512, 768)
```

Thirty-two sequences.

Each sequence contains 512 tokens.

Each token contains a 768-dimensional embedding.

---

## What Is Rank?

Rank indicates the number of dimensions.

Examples:

Scalar:

```text
5
```

Rank:

```text
0
```

---

Vector:

```text
[1, 2, 3]
```

Rank:

```text
1
```

---

Matrix:

```text
[
 [1, 2],
 [3, 4]
]
```

Rank:

```text
2
```

---

Transformer Input:

```text
(32, 512, 768)
```

Rank:

```text
3
```

---

## A Spreadsheet Analogy

Imagine:

### Scalar

One spreadsheet cell.

```text
42
```

---

### Vector

One spreadsheet row.

```text
[10, 20, 30]
```

---

### Matrix

An entire spreadsheet.

```text
Rows × Columns
```

---

### Tensor

Multiple spreadsheets stacked together.

This analogy is not perfect but helps build intuition.

---

## Images as Tensors

A grayscale image:

```text
Height × Width
```

Example:

```text
28 × 28
```

This resembles a matrix.

---

A color image:

```text
Height × Width × Channels
```

Example:

```text
224 × 224 × 3
```

Where:

```text
3
=
Red
Green
Blue
```

Now we have a tensor.

---

## Batches in Deep Learning

Neural networks rarely process one example at a time.

Instead they process batches.

Example:

```text
32 Images
```

Shape:

```text
(32, 224, 224, 3)
```

Meaning:

```text
Batch Size
     ×
Height
     ×
Width
     ×
Channels
```

This is a rank-4 tensor.

---

## Tensors in Natural Language Processing

Consider:

```text
I love AI
```

The tokenizer converts words into tokens.

Example:

```text
[101, 432, 789]
```

Tokens become embeddings.

Example:

```text
[
 [0.12, 0.55, ...],
 [0.98, 0.11, ...],
 [0.33, 0.22, ...]
]
```

This becomes a tensor.

Transformers operate directly on these tensors.

---

## Why Deep Learning Frameworks Use Tensors

Popular frameworks:

* PyTorch
* TensorFlow
* JAX

all use tensors as their primary data structure.

Everything becomes a tensor:

* Inputs
* Outputs
* Weights
* Gradients
* Embeddings
* Attention scores

---

## PyTorch Example

Creating a tensor:

```python
import torch

x = torch.tensor([
    [1, 2],
    [3, 4]
])
```

Shape:

```text
(2, 2)
```

This is a rank-2 tensor.

---

## TensorFlow Example

```python
import tensorflow as tf

x = tf.constant([
    [1, 2],
    [3, 4]
])
```

Again:

A tensor.

---

## Why GPUs Love Tensors

GPUs excel at performing operations on large blocks of numbers.

Examples:

```text
Matrix Multiplication

Tensor Operations

Parallel Computation
```

Deep Learning workloads are dominated by tensor operations.

Therefore GPUs are ideal.

---

## Tensors Inside Neural Networks

Recall:

```text
Input Layer
     ↓
Hidden Layers
     ↓
Output Layer
```

Each layer receives tensors.

Processes tensors.

Produces new tensors.

Neural networks are essentially tensor transformation systems.

---

## Tensors Inside Transformers

A transformer receives:

```text
Token Embeddings
```

These embeddings are stored in tensors.

Attention calculations produce tensors.

Feed-forward layers produce tensors.

Outputs are tensors.

Nearly every operation inside a transformer manipulates tensors.

---

## Tensors Inside GPT

Suppose GPT receives:

```text
What is Artificial Intelligence?
```

Processing pipeline:

```text
Text
 ↓
Tokens
 ↓
Embeddings
 ↓
Tensors
 ↓
Attention
 ↓
More Tensors
 ↓
Prediction
```

Internally GPT operates almost entirely on tensors.

---

## From Scalars to GPT

This is one of the most important hierarchies in AI:

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
GPT
```

Every modern AI system is built on this foundation.

---

## Common Misconceptions

### Misconception 1

Tensors are extremely complicated.

Reality:

Tensors are simply generalized containers for numbers.

---

### Misconception 2

Tensors are completely different from matrices.

Reality:

Matrices are rank-2 tensors.

---

### Misconception 3

Only researchers need to understand tensors.

Reality:

Anyone building AI systems will encounter tensors constantly.

---

## Enterprise Applications

Tensors are used in:

* Computer Vision
* NLP
* Recommendation Systems
* Fraud Detection
* Speech Recognition
* Robotics
* Autonomous Vehicles
* Large Language Models

Every modern Deep Learning system uses tensors.

---

## Key Takeaways

* Tensors generalize scalars, vectors, and matrices.
* Tensor shape describes dimensions.
* Tensor rank describes the number of dimensions.
* Images, audio, text, and videos are represented as tensors.
* PyTorch and TensorFlow are tensor-based frameworks.
* Neural networks transform tensors into other tensors.
* Transformers rely heavily on tensor operations.
* GPT models process tensors throughout inference and training.

---

## Interview Questions

### Beginner

1. What is a tensor?
2. How is a tensor related to a matrix?
3. What is tensor shape?

### Intermediate

4. What is tensor rank?
5. Why do Deep Learning frameworks use tensors?
6. How are images represented as tensors?

### Advanced

7. Explain transformer inputs using tensor shapes.
8. Why are tensor operations ideal for GPUs?
9. How do tensors flow through a neural network?

---

## Exercises

1. Identify tensor shapes for various images.
2. Determine the rank of several tensor examples.
3. Create tensors using PyTorch or TensorFlow.
4. Draw the hierarchy from scalar to tensor.
5. Explain how GPT uses tensors during inference.

---

## Chapter Summary

Tensors are the fundamental data structure of modern AI.

They generalize scalars, vectors, and matrices and provide a unified way to represent complex data such as images, language, audio, and video.

Every major Deep Learning framework is built around tensors, and nearly every operation inside neural networks, transformers, and Large Language Models involves tensor transformations.

Understanding tensors completes the first major mathematical foundation required for understanding modern AI systems.

---

## Preview of Chapter 2.5

In the next chapter, we will study Mathematical Operations for AI.

We will learn:

* Dot Products
* Matrix Multiplication
* Tensor Operations
* Transpose
* Norms
* Similarity
* Distance Metrics

These operations are the mathematical engine behind embeddings, attention mechanisms, semantic search, and transformer architectures.
