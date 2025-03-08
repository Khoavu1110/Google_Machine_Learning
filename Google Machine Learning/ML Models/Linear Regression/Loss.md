# What is loss?
- [i] Loss is a numerical metric that describes how wrong a model's predictions are.
Loss measures the distance between the model's predictions and the actual labels.
The goal of training a model is to minimize the loss, reductin to its lowest possible value.
<figure>
<img src = "https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/loss-lines.png">
<figcaption>Figure 1. Loss is measured from the actual value to the predicted value</figcaption>
</figure>

---
# Distance of Loss
In statistic and machine learning, loss measures the difference between the predicted and actual values. 
Loss focuses on the distance between the values, not the direction.
For example: if a model predicts 2, but the actual value is 5, we don't care that the loss value is -3 ($2-5 = -3$). Instead, we care that the **distance** between the values is 3. Thus, **all methods for calculating loss remove the sign**.
The two most common methods to remove the sign are:
1. Take the absolute value of the difference between the actual value and the prediction.
2. Square the difference between the actual value and the prediction.

---
# Type of Loss
In linear regression, there are four main types of loss:

| Loss Type                 | Definition                                                                                           | Equation                                                               |
| ------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| $L_1$ loss                | The sum of the absolute values of the difference between the predicted values and the actual values. | $\Sigma{\vert{\text{actual value - predicted value}\vert}}$            |
| Mean absolute error (MAE) | The average of $L_1$ losses across a set of examples.                                                | $\frac{1}{N} \Sigma{\vert \text{actual value - predicted value}\vert}$ |
| $L_2$ loss                | The sum of the square difference between the predicted values and the actual values.                 | $\Sigma{\text{(actual value - predicted value)}^2}$                    |
| Mean square error (MSE)   | The average of $L_2$ losses across a set of examples.                                                | $\frac{1}{N} \Sigma{\text{(actual value - predicted value)}^2}$        |

> [!note] Note
> The functional difference between $L_1$ loss and $L_2$ loss (or between MAE and MSE) is squaring.
> When the difference between the prediction and label is large, squaring makes the loss even larger. Vice versa, when the difference is small (less than 1), squaring makes the loss even smaller.

> [!example] Calculating Loss Example
> Using the previous best fit line, we will calculate $L_2$ loss for a single example. From the best fit line, we had the following values for weight and bias:
> - Weight: -3.6
> - Bias: 30
> If the model predicts that a 2,370-pound car gets 21.5 miles per gallon, but it is actually gets 24 miles per gallon, we would calculate the $L_2$ loss as follows:
> 
> | Value        | Equation                                                        | Result |
> | ------------ | --------------------------------------------------------------- | ------ |
> | Prediction   | $\text{bias+(weight}*\text{feature value)}$<br>$30+(-3.6*2.37)$ | 21.5   |
> | Actual value | $\text{label}$                                                  | 24     |
> | $L_2$ loss   | $\text{(actual value - predicted value)}^2$<br>$(24-21.5)^2$    | 6.25   |
> In this example, the $L_2$ loss for that single data point is 6.25.

---
# Choosing A Loss




