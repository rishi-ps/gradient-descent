# Gradient Descent for Linear Regression

This project implements **Gradient Descent** (**"Batch Gradient Descent"** to be specific) to find the optimal parameters for **Linear Regression**. Linear regression is a statistical method used to model the relationship between a dependent variable $$( y \)$$ and one or more independent variables $$( X \)$$.

This project is a simpler implementation of Gradient Descent for Linear Regression presented in [DeepLearning.AI's Machine Learning Specialization](https://www.coursera.org/learn/machine-learning?specialization=machine-learning-introduction). 

## What is Gradient Descent?

Gradient Descent is an optimization algorithm used to minimize a cost function by iteratively moving towards the direction of the steepest descent. In the context of linear regression, the cost function we aim to minimize is the **Mean Squared Error (MSE)** between the predicted values and the actual values.

The equation for a simple linear regression model is:

$$
y = \theta_0 + \theta_1 x
$$

Where:
- $$( \theta_0 \)$$ is the intercept term.
- $$( \theta_1 \)$$ is the slope term.

$$( \theta_0 \)$$ and $$( \theta_1 \)$$ are the parameters to be learned.

The cost function $$( J(\theta) \)$$ for linear regression is given by:

$$
J(\theta_0, \theta_1) = \frac{1}{2m} \sum_{i=1}^{m} \left(h_{\theta}(x^{(i)}) - y^{(i)}\right)^2
$$

Where:
- $$( m \)$$ is the number of training examples.
- $$( h_{\theta}(x) = \theta_0 + \theta_1 x \)$$ is the hypothesis function.

The goal is to find the values of $$( \theta_0 \)$$ and $$( \theta_1 \)$$ that minimize $$( J(\theta) \)$$.

## Gradient Descent Algorithm

Gradient Descent updates the parameters iteratively using the following rule:

$$
\theta_j := \theta_j - \alpha \frac{\partial}{\partial \theta_j} J(\theta)
$$

Where:
- $$( \alpha \)$$ is the learning rate, controlling the step size.
- $$( \frac{\partial}{\partial \theta_j} J(\theta) \)$$ is the derivative (gradient) of the cost function with respect to $$( \theta_j \)$$.

We update the variable $$\theta_j$$ in such a manner because, if the slope, i.e $$\frac{\partial}{\partial \theta_j} J(\theta)$$ is positive, the direction of steepest descent is to the left. To move to the left, we reduce $$\theta_j$$. Hence the subtraction. In contrast, if $$\frac{\partial}{\partial \theta_j} J(\theta)$$ is negative, the direction of steepest descent is to the right. In order to move to the right, we need to add to $$\theta_j$$. This is taken care of by the same formula because the negative sign of the $$\frac{\partial}{\partial \theta_j} J(\theta)$$ and the negative sign before $$\alpha$$ multiply to give a positive sign. 

### Steps to Apply Gradient Descent:
1. Initialize $$( \theta_0 \)$$ and $$( \theta_1 \)$$ randomly or with zeros.
2. Compute the gradient of the cost function with respect to each parameter.
3. Update the parameters using the gradient descent update rule.
4. Repeat steps 2-3 for a specified number of iterations or until convergence.
