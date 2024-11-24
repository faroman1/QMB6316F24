# Assignment 3

Following the instructions in the document ```QMB6316_assignment_03.pdf``` above, 
enter your responses in the code blocks shown below.


In this exercise, we will follow an approach different than that taken in class. 
We will first estimate a model with our choices of functional form, then consider exclusions of insignificant variables from the full model. 
Note that this approach allows for inclusion of possibly irrelevant variables and avoids excluding any relevant variables. 


At each stage, use the best model that you have found so far, 
incorporating the findings from the answer to the previous question.




a. Estimate a regression model that uses all available variables.
	Make sure to choose a reasonable transformation of the dependent variable, 
	such as the logarithmic transformation, if necessary.
	
```
Call:
lm(formula = log_saleprice ~ horsepower + squared_horsepower + 
    age + enghours + cab + diesel + fwd + johndeere + spring + 
    summer + winter, data = tractor_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-1.75656 -0.23453  0.05714  0.27916  0.72523 

Coefficients:
                     Estimate Std. Error t value Pr(>|t|)    
(Intercept)         8.892e+00  1.118e-01  79.523  < 2e-16 ***
horsepower          1.124e-02  1.079e-03  10.421  < 2e-16 ***
squared_horsepower -1.583e-05  2.279e-06  -6.948 2.89e-11 ***
age                -3.455e-02  3.479e-03  -9.929  < 2e-16 ***
enghours           -4.157e-05  9.685e-06  -4.292 2.49e-05 ***
cab                 4.644e-01  7.074e-02   6.564 2.76e-10 ***
diesel              1.308e-01  9.351e-02   1.399  0.16299    
fwd                 2.669e-01  5.914e-02   4.513 9.64e-06 ***
johndeere           2.896e-01  7.250e-02   3.995 8.41e-05 ***
spring             -1.159e-01  6.559e-02  -1.767  0.07833 .  
summer             -1.981e-01  6.433e-02  -3.080  0.00229 ** 
winter             -1.879e-01  7.188e-02  -2.614  0.00946 ** 
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.402 on 264 degrees of freedom
Multiple R-squared:  0.7933,	Adjusted R-squared:  0.7847 
F-statistic: 92.12 on 11 and 264 DF,  p-value: < 2.2e-16




```

Does this seem to be a reasonable model, as opposed to using average tractor prices? 
	That is, is the R-squared or the R-bar-squared reasonably high?

```
When compared, the log R-Squared is higher for model 7 with a 0.7933 versus average prices in model 1 with an R-Squared of 0.6073. Model 7 seems to be a reasonable model to use.



```


b. Which variables seem to help explain used tractor prices? 
	Which have positive and negative relationships with tractor prices?
	Did you find any variables that do not have statistically significant coefficients under this specification?

```
Horsepower = (+) squared_horsepower = (-) age = (-) enghours = (-) cab = (+) diesel = (+) fwd = (+) johndeere = (+) spring = (-) summer = (-) winter = (-) age:johndeere = (+)
All variables except diesel and spring are statistically significant.



```



c. Before making any reductions to your model, revise the model specification first
	by considering nonlinear specifications.
	A used tractor dealer tells you that overpowered used tractors are hard to sell, since they consume more fuel. 
      Tractor prices often increase with horsepower, up to a point, but beyond that they decrease. 
      To incorporate this advice, you create and include a variable for squared horsepower and include that in a new regression model. 
      

```
Call:
lm(formula = log_saleprice ~ horsepower + squared_horsepower + 
    age + enghours + cab + diesel + fwd + johndeere + spring + 
    summer + winter, data = tractor_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-1.75656 -0.23453  0.05714  0.27916  0.72523 

Coefficients:
                     Estimate Std. Error t value Pr(>|t|)    
(Intercept)         8.892e+00  1.118e-01  79.523  < 2e-16 ***
horsepower          1.124e-02  1.079e-03  10.421  < 2e-16 ***
squared_horsepower -1.583e-05  2.279e-06  -6.948 2.89e-11 ***
age                -3.455e-02  3.479e-03  -9.929  < 2e-16 ***
enghours           -4.157e-05  9.685e-06  -4.292 2.49e-05 ***
cab                 4.644e-01  7.074e-02   6.564 2.76e-10 ***
diesel              1.308e-01  9.351e-02   1.399  0.16299    
fwd                 2.669e-01  5.914e-02   4.513 9.64e-06 ***
johndeere           2.896e-01  7.250e-02   3.995 8.41e-05 ***
spring             -1.159e-01  6.559e-02  -1.767  0.07833 .  
summer             -1.981e-01  6.433e-02  -3.080  0.00229 ** 
winter             -1.879e-01  7.188e-02  -2.614  0.00946 ** 
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.402 on 264 degrees of freedom
Multiple R-squared:  0.7933,	Adjusted R-squared:  0.7847 
F-statistic: 92.12 on 11 and 264 DF,  p-value: < 2.2e-16



```


  c.i) Hypothesize the signs for the coefficients on horsepower 
	under this scenario. 
		What should be the sign of the coefficient for horsepower? 
		What sign do you expect for squared horsepower?
      
```
I expect horsepower to be positive and squared horsepower to be negative. 


```

  c.ii) Perform 1-sided t-tests of the hypotheses for each of the horsepower coefficients. 
That is, are the t-statistics higher than 1.96, with the same sign as you hypothesized?

```

My hypothesis proved to be accurate, horsepower was positive while squared horsepower proved to be negative.
All variables except diesel and spring were found to be statistically significant. Horsepower, 
cab, diesel, fwd, and johndeere were positive while squared horsepower, age, enghours, spring, summer, and winter were negative.


```

  c.iii) Compare the model with or without the quadratic functional form for horsepower.
            Which model do you recommend? 
		Be sure to cite evidence to support your choice. 
		Specifically, check the four specification criteria: 
		statistical significant $t$-statistics, 
		an increase in R-squared, 
		a good theoretical justification, and 
		no large change in the other coefficients.

```
I recommend the model with the quadratic functional form for horsepower. Without this function, the model 
saw a decrease in the Multiple R-Squared and Adjusted R-Squared. Removing the horsepower function changed the squared horsepower
from negative to positive and changed diesel from being statistically insignificant to statistically significant. 



```


d. Again, use the best model that results from the answer to the previous question to address further questions.
	Use the model you have so far to test that the time of year has no effect on the sale of tractors.
	That is, test whether the t-statistics on the seasonal indicators are statistical significant. 
	Is there evidence that tractor prices follow a seasonal pattern? 

```
All three seasons prove to be negative. Summer and Winter are proven to be statistically significant, while Spring
proves to be statistically insignificant. With the highest estimate of the seasons being in summer and the values 
decreasing in the following seasons, there can be reason to believe that there is some evidence to prove a seasonal pattern for 
tractor prices.


```
	
	
e. Finally, consider another modification to your model. 
	Some say that John Deere tractors hold their value longer than other tractors. 
      This raises the question of whether an additional hour of use affects the value of a John Deere tractor 
	differently than for tractors of other brands. 
	You can test this by including an interaction with ```age:johndeere``` in the regression.
	
```
Call:
lm(formula = log_saleprice ~ horsepower + squared_horsepower + 
    age + enghours + cab + diesel + fwd + johndeere + age:johndeere + 
    spring + summer + winter, data = tractor_full)

Residuals:
     Min       1Q   Median       3Q      Max 
-1.77473 -0.23473  0.05023  0.27762  0.73218 

Coefficients:
                     Estimate Std. Error t value Pr(>|t|)    
(Intercept)         8.903e+00  1.129e-01  78.844  < 2e-16 ***
horsepower          1.130e-02  1.083e-03  10.435  < 2e-16 ***
squared_horsepower -1.587e-05  2.282e-06  -6.957 2.75e-11 ***
age                -3.526e-02  3.628e-03  -9.719  < 2e-16 ***
enghours           -4.214e-05  9.728e-06  -4.332 2.10e-05 ***
cab                 4.661e-01  7.085e-02   6.578 2.56e-10 ***
diesel              1.295e-01  9.362e-02   1.384  0.16762    
fwd                 2.673e-01  5.919e-02   4.515 9.55e-06 ***
johndeere           2.032e-01  1.425e-01   1.425  0.15522    
spring             -1.210e-01  6.604e-02  -1.832  0.06810 .  
summer             -2.019e-01  6.461e-02  -3.125  0.00198 ** 
winter             -1.890e-01  7.197e-02  -2.626  0.00914 ** 
age:johndeere       4.927e-03  6.990e-03   0.705  0.48155    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.4024 on 263 degrees of freedom
Multiple R-squared:  0.7937,	Adjusted R-squared:  0.7843 
F-statistic: 84.32 on 12 and 263 DF,  p-value: < 2.2e-16



```

Test the hypothesis, at the 5 percent level of significance, that the slope for engine hours differs by brand. 

Does an additional hour of use affect the price of a John Deere tractor
differently than tractors of other brands?
	
```
No, an additional hour proved to be statistically insignificant in proving the proposed theory.



```
	
	
	
