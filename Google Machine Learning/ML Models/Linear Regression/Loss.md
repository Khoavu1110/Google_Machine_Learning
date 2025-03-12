# What Is loss?

- [i] **Loss** is a numerical metric that <u>describes how wrong a model's predictions are</u>.
Loss **measures** <u>the distance between the model's predictions and the actual labels</u>.
The **goal** of training a model is to <u>minimize the loss, reduction to its lowest possible value</u>.

<figure>
	<center>
		<img src = "https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/loss-lines.png">
		<figcaption> 
			<b>Figure 1.</b> Loss is measured from the actual value to the predicted value
		</figcaption>
	</center>
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

| Loss Type                                                    | Definition                                                                                           | Equation                                                               |
| ------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| **$L_1$ loss**                                               | The sum of the absolute values of the difference between the predicted values and the actual values. | $\Sigma{\vert{\text{actual value - predicted value}\vert}}$            |
| **[[Mean Absolute Error (MAE)\|Mean absolute error (MAE)]]** | The average of $L_1$ losses across a set of examples.                                                | $\frac{1}{N} \Sigma{\vert \text{actual value - predicted value}\vert}$ |
| **$L_2$ loss**                                               | The sum of the square difference between the predicted values and the actual values.                 | $\Sigma{\text{(actual value - predicted value)}^2}$                    |
| **Mean square error (MSE)**                                  | The average of $L_2$ losses across a set of examples.                                                | $\frac{1}{N} \Sigma{\text{(actual value - predicted value)}^2}$        |

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

- [k] Deciding whether to use MAE or MSE can depend on the dataset and the way you want to handle certain predictions.
Most features in a dataset typically fall within a distinct range.
- [i] An outlier can also refer to <u>how far off a model's predictions are from the real values</u>.
- [I] When choosing the best loss function, <u>consider how you want the model to treat outliers</u>.
	- For instance: MSE moves the model more toward the outliers, while MAE doesn't.
	- $L_2$ loss incurs a much higher penalty for an outlier than $L_1$ loss.
		- For example:
	<figure>
		<center>
			<img src = "Pasted image 20250307225801.png">
			<figcaption>
			<b>Figure 10</b>. A model trained with MSE moves the model closer to the outliers.
			</figcaption>
		</center>
	</figure>		
	
	<figure>
		<center>
			<img src = "		Pasted image 20250307230025.png">
			<figcaption>
			<b>Figure 11</b>. A model trained with MAE is farther from the outliers.
			</figcaption>
		</center>
	</figure>
	The image show a model trained using MAR and a model trained using MSE. The red line represents a fully trained model that will be used to make predictions.
	Note the relationship between the model and data:
	- **MSE**: The model is closer to the outliers but further away form most of the other data points.
	- **MAE**: The model is further away from the outliers but closer to most of the other data points.

> [!question] Check your understanding
> Consider the following two plots:
> <figure><center><img src = "Pasted image 20250307230744.png"><figcaption><b>Dataset 1</b></figcaption></center></figure>
> 
> 
> <figure><center><img src = "Pasted image 20250307230801.png"><figcaption><b>Dataset 2</b></figcaption></center></figure>
> 
> Which of the two data sets has the higher Mean Square Error (MSE)?
> >- [ ] Dataset 1
> > - [x] Dataset 2
