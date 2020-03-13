# Introduction

## Turing Testing
Developed by Alan Turing in 1950. A test to verify if the one we're interact to is a real human or an AI.

### Equivalence
- Weak Equivalence: With different underlying (internal) process to a human being.
- Strong Equivalence: With same internal process to a human being.

## AI
### Traditional AI

### Computational Intelligence
- Not recognized as a part of AI in 1990s.
- Most well-known technique: **neural networks**.
- No distinguish AI and CI nowadays.

### Machine Learning
Give computers the ability to learn without being explicitly programmed.
#### Supervised Learning
Learning a function that maps an input to output. We collects a lot of data in **input-output pairs**.

We can deal with following kinds of problems:
- Classification problems: Used to **classify** the category of an input data.Out put variable is a category, e.g. 'yes/no', '1~9'
- Regression problem: Used to **predict** some value according to the input data. When output is a continuous value, e.g. 'salary', temperature.

Using:
- Prediction of future cases
- **Outlier** detection
- Knowledge extraction

##### Classification
```
Algorithm: To determine a cat.

Input: (A cat photo)

Ouput: Yes

Training data set: [
  (cat1.png, true),
  (dog1.png, false),
  (cat2.png, true),
  (cat3.png, true),
  (horse.png, false),
  ...
]
```

##### Regression Problem
BMI prediction
```
Training Data: [BMI, Fat%]
example: [
  (15, 15%),
  (20, 30%),
  (25, 35%),
  (30, 40%),
  ...
]
```

#### Unsupervised Learning
A technique to model probability densities over inputs; there's **no outputs** in unsupervised learning.

Two major approadches:
- Principal componenet(PCA or AE):
  - Dimension reduction
  - Generate synthetic pictures
- Cluster analysis(k-means or SOFM):
  - Example: VQ used for image compression

#### Reinforcement Learning
Reinforcement learning is used to lear a policy of context. For example, in a chase game, we have some policies to choose the next move which fits the current context; Reinforcement Learning is to find out the policies.

Approaches
- Valued-based(e.g. Q learning)
- Policy-based(e.g. PPO)
- (Combination of above two)

Used cases:
- Playing games.
- Training robot, autonomous car.
