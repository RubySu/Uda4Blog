# Udacity - Write-A-Data-Science-Blog-Post

## Motivation for the project
Germany as a highly developed country with a very high standard of living, it offers social security and a universal health care system, environmental protections, and a tuition-free university education. You may have heard statements like "you can find a most stable job with high salary in Germany" or "woman can get same salary as man in Germany." Now, I would like to interpret these questions by analyzing data from Stackoverflow's 2017 Annual Developer Survey. 
  
What does the data answer?    
Stack overflow logoThe survey data covers 64,000 reviews from 213 countries and territories. The survey aims to understand multiple aspects of jobs related to software development and data analytics. There were more than 150 questions as a part of the survey, including:    
- " Which of the following best describes you?"
- " Which of the following best describes your current employment status?"
- " Which of the following best describes the highest level of formal education that you've completed?"

## Business Understanding
From Stackoverflow’s 2017 Annual Developer Survey, I am going to answer some questions:   
- As a professional developer, who are the most educated people in Germany?  
- What is the difference in terms of salary by gender in Germany?  
- What aspects correlate well to career satisfaction?  

## Data Understanding
There were 19102 total survey records with 153 different features (excluding Respondent).
- A little less than 20% professional developers have Master’s degree, and more than 13% people got Bachelor’s degree.
- From the plot, we can learnt that man earned higher salary than woman with higher formal education. There is a big salary gap (~30000) in Doctoral degree.
- Professional developer, job satisfaction shows high coefficient(>0.5) which would be high correlated to career satisfaction。

## Prepare Data
Loading data from survey_results_public.csv. To answer the first and second questions, we use pandas to slice the dataset into subsets.
- We took German in Country, Professional developer in Professional, aggregate counts by FormalEducation, then plot the data. 
- We took German in Country, Professional developer in Professional, aggregate counts by Gender and FormalEducation, then took the mean value of salary to plot it.
- To answer this question we need to clean data first. We took CareerSatisfaction as Y, dropped Respondent from X, impute numeric features and dummy categorical features.

## Data Modeling
To answer the third question, a optimized linear regression model has been generated.   
Using find_optimal_lm_mod function to build LinearRegression model, by changing different cutoffs to optimize the model, cutoffs pertains to the number of missing values allowed in the used columns. Here we chose Rsquared score to evaluate results and find the inflection point.  
Then we used coefficient weights from LinearRegression.coef_ as indicator and plot, high coefficient means high correlation with career satisfaction.

## Conclusion
1.Master's degree and Bachelor's degree are the mainstream of professional developer in Germany which means higher education is important to become a professional developer.   
2.We then looked at how different in terms of salary between male and female. This showed that male earn more in higher education and there is not too much correlation between higher education and salary for female.    
3.Finally, we found that the people who had job with good communication and professional skill are usually satisfied with their careers .  

## File Structure

- UdacityL4.ipynb : Detail data analysis main file.
- model_func.py : including find_optimal_lm_mod model optimization function and was called by UdacityL4.


## Medium Blog Post
https://medium.com/@rem_lol/how-do-you-become-a-professional-developer-in-germany-ce5bfa591823?source=friends_link&sk=a4d41000a97d4faf75046196bae7e03b

## Source Data
https://insights.stackoverflow.com/survey

## Libraries used
numpy  
pandas  
matplotlib  
sklearn
seaborn
python 3.X
