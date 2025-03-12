#metric

# What Is Mean Absolute Error
- [i] The average loss per example when $L_1$ ([[L1 Loss|L1]]) loss is used.

---
# How To Calculate?

Calculate Mean Absolute Error as follows:
1. Calculate the $L_1$ loss for a batch.
2. Divide the $L_1$ loss by the number  of examples in the batch.
$$
\text{Mean Absolute Error} = \frac{1}{n} \Sigma_{i=0}^{n} |y_i-\hat y_i |
$$
	where:
		$n$ is the number of examples.
		$y$ is the actual value of the label.
		$\hat y$ is the value that the model predicts for y.

---
# Example 

| <center>Actual value of example</center> | <center>Model's predicted value</center> | <center>Loss (difference between actual and predicted</center> |
| ---------------------------------------- | ---------------------------------------- | -------------------------------------------------------------- |
| <center>7</center>                       | <center>6</center>                       | <center>1</center>                                             |
| <center>5</center>                       | <center>4</center>                       | <center>1</center>                                             |
| <center>8</center>                       | <center>11</center>                      | <center>3</center>                                             |
| <center>4</center>                       | <center>6</center>                       | <center>2</center>                                             |
| <center>9</center>                       | <center>8</center>                       | <center>1</center>                                             |
|                                          |                                          | 8 = $L_1$ loss                                                 |

So, $L_1$ loss is 8 and the number of examples is 5
	$\therefore$ the Mean Absolute Error is:
``` python
# Mean Absolute Error = L_1 loss / Number of examples
Mean Absolute Error = 8/5 
# Mean Absolute Error = 1.6
```
	