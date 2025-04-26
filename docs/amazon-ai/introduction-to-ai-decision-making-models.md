---
sidebar_position: 5
---

# Introduction to AI Decision Making Models

## AI and machine learning basics

- AI:
  - Recognizes patterns
  - Understands language
  - Makes Decisions
- Machine Learning:
  - Learn from examples over time
  - Apply Learning to new tasks

### Example: Creating a SPAM Filter

- Training Data
  - Label the emails SPAM and Not SPAM
- Pre-process data
  - Clean: removes the irrelevant data or noise
  - Normalize: the data input is in a consistent structure and format, which is treated uniformly by the model
- Train the model
  - Learn patterns from the training data
- Trained Spam Filter
  - Pattern to recognize Spam

#### False Positives

- An email is mistakenly classified as SPAM because it shares characteristics or patterns of a spam email.

#### No ML is perfect

- Errors can occur
- Requires people to critically evaluate the output

## Decision Trees

- **Decision Trees** help classify data and predict outcomes by breaking down this decision-making process into series of simple questions.
- A **tree** is a data structure that organizes data hierarchically.
  - It consists of a series of points called nodes.
  - The tree is upside of a natural tree.
  - The root is at the top (root node, level 0)
  - The leaves at the bottom.
- Child Nodes: connected below another node, like branches growing out
- Parent node: A node that has child nodes below it
- Leaf Nodes: nodes at the bottom of the tree with no children. These represent final decisions or outcomes.
- Internal Nodes: nodes that have at least one child node as well as a parent node. They are intermediate decision points in the tree
- A Decision tree is a specialized type of tree in ML to make decisions based on input data.
- **Input Data**: info or observations provided to the model so it can either learn during training or make decisions based on the rules it learned.
- Decision Trees mimic how humans make decisions by splitting data at each node based on specific conditions.
- In a decision tree:
  - Internal nodes: Represent questions or conditions.
  - Branches: Represent possible answers or outcomes of a condition.
  - Leaf nodes: Represent the final decision or result.
- **Features**: characteristics under consideration
  - Their values are called **Feature Values**
- The goal of a decision tree is to split data into subsets based on feature values until a clear decision can be made.
- **Subsets** are smaller groups of data created by dividing the original dataset according to specific conditions.
- In Summary, Decision Trees:
  - Purpose: Facilitates decision-making by asking a series of step-by-step questions
  - Nodes: Represents questions in nodes and answers at the endpoints (leaves).
  - Structure: Uses a sequence of "yes" or "no" questions to follow a path and reach a decision.
  - Example: Predicts outcomes, like determining if a student will pass or fail based on study hours and attendance.
- In Contrast, a general tree, think of files and folders in a computer as an example.

### Is reverse navigation in decision trees possible?

- Backtracking or navigating backward is not possible in a decision tree.
- Once a decision tree splits the data and makes a decision at a node, it continues forward along a specific path.
- It cannot reverse the decision or return to revisit previous nodes.
- The direction can only be from the root towards the leaf and never be reversed, which means it’s **unidirectional**, moving from the root to a leaf node.
- Unidirectional navigation offers the following advantages:
  - Every path leads to a leaf node
  - Handling all possible outcomes:
  - Exhaustive conditions: account for all possible values of a feature at each split.
  - Default behavior: If a decision tree encounters data outside the scope of its training data, it still tries to follow the closest matching path to reach a leaf node, though the result may not be as accurate.
  - No infinite loops

### Binary Decision Trees

- Maximum of two child nodes
- Each decision splits the data into two subsets based on a binary condition (e.g., "Yes" or "No").

### Multiway decision trees

- A multiway decision tree is characterized by `k` child nodes, where `k` is the number of unique values in a categorical feature.
  - For example, for a feature like "Weather" with possible values of “Sunny,” “Rainy,” or “Cloudy,” each node can have up to three child nodes; that is, one for each unique value.

### Continuous feature

- When a feature or characteristic can take any value in a range
- For example, a person’s age can be any value in the range of 1 to 100.

### Discretized feature

- If a continuous feature or characteristic is split into categories, it is known to be discretized.
- For example:
  - Child: Age from 1 to 18 years
  - Young adult: Age from 19 to 35 years
  - Adult: Age from 36 to 80 years
  - Seniors: Age above 80 years

### Pros & Cons of Decision Trees

- Advantages:
  - Easy to understand
  - Works with different data such as numerical and categorical data
  - Non-parametric: They don’t assume a specific distribution of data, where data may not follow standard distributions.
- Disavantages:
  - Overfitting: Decision trees can become overly complex, capturing noise in the data rather than the underlying pattern.
    - Noise refers to patterns that are not meaningful to the decision-making process but can influence it.
  - Instability: A slight change in the data can lead to a completely different tree structure.
  - Bias towards features with more levels: Decision trees can be biased toward features with many unique values.

## Random Forests

- Random Forests:
  - Group of Decision Trees
  - Combined Results
- Overfitting: failing to generalize to new data
- Random Forests overcome the issue of overfitting.
- The final result is the average output.

### Bagging

- Bagging (Bootstrap Aggregating): the technique of each tree in a random forest being trained on a different random subset, characteristic, or feature of the data
  - Reduces the chances of overfitting by ensuring that each tree has a unique perspective on the data

### Feature Randomness

- **Feature Randomness**: at each split in a tree, only a random subset of the features is considered.
  - Adds a layer of randomness, ensuring that the trees don't all appear the same and rely too heavily on specific features.

### Advantages

- Reduced overfitting
- Improved accuracy
- Versatility
- Handle Missing Data
- Numerical & Categorical Features

## Neural Networks

- A **Neural Network** is a computation model inspired by the human brain
- 3 main steps:
  - Input layer: starting point to pass raw data like an image
  - Hidden layers: data passes through the input layer to intermediate stations, where the data is processed and transformed.
  - Output layers: the network produces the result
- Each layer consists of **neurons (nodes)**, which are interconnected and work together to process the input
- A neuron is the smallest computational unit in a neural network
- Neurons mimics biological neurons in the brain
- A neuron receives input from either the input layer or previous neurons and processes them and makes decisions on whether it should be sent forward to the next layer or not.

## Neural network in action

This example we are sorting fruits into categories (color, size, and shape).

### Input Layer

- The input layer is where the raw features are fed into the network.
- Input features:
  - Color: Red or Not Red
  - Size: Small or Medium
  - Shape: Is it like an apple or not?

### Hidden Layer

- The hidden layers are where the network starts processing the inputs to find patterns.
- Each neuron in the hidden layer combines the inputs, applies values known as weights (signifying the importance) to each input, and then uses an activation function to decide whether to pass the information forward.
  - weights help the network prioritize certain features over others when making its decision.
- In this example, one neuron can check for color, another checks for size, and the last neuron checks for shape.

### Output Layer

- The output layer takes the combined information and produces the final prediction.

### Scores, weights, and the activation function

1. Scoring the outputs from the hidden layer: Each neuron outputs a score or signal, which represents the likelihood of a particular feature matching the target. These scores will then be combined to make a prediction.
2. Assigning the weighted scores: Each hidden layer output is assigned a value called a weight based on its importance.
3. Summing the weighted scores: this will produce the combined score from the hidden layer. This weighted summation gives the final "confidence score" for the prediction.
4. Passing through the activation function: the data is passed from the hidden layer to the output layer. In the output layer, the combined score is passed through an activation function.

- For example, an example of an activation function that produces a result between 0 and 1 is Sigmoid.

```
Sigmoid = 1 / ( 1 + e^(-x) )
```

- There are other functions beyond that like ReLU (Rectified Linear Unit), Tanh (Hyperbolic Tangent), ELU (Exponential Linear Unit), Softmax, Swish

5. Making a final decision in the output layer: The output layer uses the activation results to make the final decision.

### Learning from mistakes: Error correction

- A neural network learns by checking its mistakes and its weights, like a feedback loop, and trying again with the adjusted weight for the different features.
