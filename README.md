# Alphabet Soup 
## Purpose 
The prupose of the project is to find out where to invest money. 
## Results: 
### What variable(s) are considered the target(s) for your model? 
['APPLICATION_TYPE', 'AFFILIATION','CLASSIFICATION','USE_CASE','ORGANIZATION','INCOME_AMT','SPECIAL_CONSIDERATIONS']
### What variable(s) are considered to be the features for your model? 
'INCOME_AMT' 'CLASSIFICATION', 'ORGANIZATION'
### What variable(s) are neither targets nor features, and should be removed from the input data? 
Application Type, 'SPECIAL_CONSIDERATIONS','STATUS'
## Compiling, Training, and Evaluating the Model
### How many neurons, layers, and activation functions did you select for your neural network model, and why? 
I chose 3 layers, neurons and activation functions. I did try to use more, but it negativley effected my model when I changed it from 3.  
### Were you able to achieve the target model performance? 
No
### What steps did you take to try and increase model performance? 
1. application_df['USE_CASE'] = application_df['USE_CASE'].replace('CommunityServ', 'Other') & 
2. application_df['USE_CASE'] = application_df['USE_CASE'].replace('Heathcare', 'Other') & 
3. application_df['ORGANIZATION'] = application_df['ORGANIZATION'].replace('Co-operative', 'Other')    
I tried to put the 'CommunityServ', 'Co-operative', 'Heathcare' numbers in 'Other' in hopes of getting rid of any outliers.  
4. Deliverable 3: Increase accuracy, attemp #3
income_amt_replace = application_df["INCOME_AMT"].value_counts()[application_df["INCOME_AMT"].value_counts() < 1000].index.to_list()
income_amt_replace.append("0")
for i in income_amt_replace:
    application_df["INCOME_AMT"] = application_df["INCOME_AMT"].replace(i, "Other")
application_df["INCOME_AMT"].value_counts() 
I attempted to put anything with a value less that 1000 into 'Other'
5. I changed the batch_size
## Summary.  
Accuracy was btwn btwn 73 and 74 % 
loss was btwn 0.54 and 0.55 

## recommendation on using a different model to solve the classification problem, and justification 
I would maybe try to adjust the activation or Density of the model. 
