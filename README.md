# Tea-and-Sugar-Project
This file contains all relevant R code used for my Tea, Sugar, and Numbers Project. The project was carried out by using a pooled t-test with A/B testing.

1. Arranging the data and creating a table 

tea1 = c(184, 211, 147, 207, 221, 191, 200, 191, 163, 152)
sugar1 = c(195, 207, 181, 174, 210, 203, 177, 188, 177, 167)
data = data.frame(tea1, sugar1)
knitr::kable(data, "pipe", col.names = c("Tea Buffer", "Sugar Buffer"),
align = c("c", "c"))


2. Calculating corresponding Standard Deviations to choose the correct test type

sd(tea1) 
sd(sugar1) 

sd(tea1)/sd(sugar1) 

t.test(tea1, sugar1, paired = FALSE, var.equal = TRUE)

3. Calculating Pooled Variance

{(10-1)*sd(tea1)^2} + {(10-1)*sd(sugar1)^2} 

7789/10+10-2 = 432.722

4. Calculating the t-statistic

mean(tea1) - mean(sugar1) - 0
sqrt( 432.722 * ( (1/10) + (1/10) ) ) 

#t-statistic = -1.2/9.302926 = -0.1289917

5. Calculating the P-value 

pt(-0.12899, 18) 

2*0.449398

#p-value for this test = 0.898796











