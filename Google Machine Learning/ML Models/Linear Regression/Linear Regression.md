#Model

- [k] Learning Objective:
	- [*] Explain what a loss function and how it works.
	- [*] Define and describe how gradient descent finds the optimal model parameters.
	- [*] Describe how to tune hyper parameters to efficiently train a linear model.
# What is Linear Regression?

- [i] Linear regression is a statistical technique used to find the relationship between variables. In an ML context, linear regression finds the relationship between [[Feature|features]] and a [[Label|label]].

---
# Linear Regression Equation

In algebraic terms, the model would be defined as $y=mx+b$, where:
- $y$ is the value we want to predict.
- $m$ is the slope of the line.
- $x$ is the input values.
- $b$ is the y-intercept.
 In ML, we write the equation for  a linear regression model as follow:
$$
y'=b+w_1x_1
$$
where:
- $y'$ is the predicted label - the output.
- $b$ is the [[Bias|bias]] of the model.
	- [i] Bias is the same concept as the y-intercept in the algebraic equation for a line. In ML, bias is sometimes referred to as $w_0$. Bias is a [[Parameter|parameter]] of the model and is calculated during training.
- $w_1$ is the [[Weight|weight]] of the feature.
	- [i] Weight is the same concepts as the slope m in the algebraic equation for a line. Weight is a [[Parameter|parameter]] of the model and is calculated during training.
- $x_1$ is a [[Feature|feature]] - the input.
*During training, the model calculates the weight and bias that produce the best model.*
<figure>
	<img src = "https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/equation.png">
	<figcaption> Figure 1. The equation y' = b + w1x1, with each component annotated with its purpose. </figcaption>
</figure>

---
# Models With Multiple Features

For example, a model that relies on five features would be written as follows:
$$
y'=b+w_1x_1+w_2x_2+w_3x_3+w_4x_4+w_5x_5
$$
Therefore, an example of a model that predicts gas mileage could use features such as:
- Engine displacement
- Acceleration
- Number of cylinders
- Horsepower
Would be written as:
<figure>
	<img src = "https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/equation-multiple-features.png">
	<figcaption>Figure 2. Linear regression equation with five features.</figcaption>
</figure>

---
> [!Question] Check your understanding
> What parts of the linear regression equation are updated during training?
> - [ ] The feature values
> - [ ] The prediction
> - [x] The bias and weights

