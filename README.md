# Analyst-python:Instacart Grocery Basket Analysis 

## INTRODUCTION: ![image](https://user-images.githubusercontent.com/108523069/177024265-bcb6b603-08fe-492d-8084-b55fb84fce82.png)
Instacart, an online grocery store that operates through an app. Instacart already has very good sales, but they want to uncover more information about their sales patterns.The Instacart stakeholders are most interested in the variety of customers in their database along with their purchasing behaviors. They assume they can't target everyone using the same methods,and they’re considering a targeted marketing strategy. They want to target different customers with applicable marketing campaigns to see whether they have an effect on the sale of their products.

## OBJECTIVES OF THE PROJECT: 
Our task is to perform an initial data and exploratory analysis of some of their data in order to derive insights and suggest strategies for better segmentation based on the provided criteria.The Instacart stakeholders are most interested in the variety of customers in their database along with their purchasing behaviors. Our analysis will inform what this strategy might look like to ensure Instacart targets the right customer profiles with the appropriate products.

## DATASETS:
- Departments
- Orders
- Products
- Customers 
- Orders_products_prior
- link (https://s3.amazonaws.com/coach-courses-us/public/courses/data-immersion/A4/A4_Data_Assets/customers.zip)

## Citation: “The Instacart Online Grocery Shopping Dataset2017”, Accessed from (https://www.instacart.com/datasets/grocery-shopping-2017) on<16/05/2022>.


## Libraries used:
- Pandas
- Numpy
- os
- matplotlib
- Seaborn
- scipy

## Some script cells:
### Creating an 'age_group' column.
df_retained.loc[(df_retained['age'] >= 18) & (df_retained['age'] <= 25), 'age_group'] = '18 - 25'
df_retained.loc[(df_retained['age'] >= 26) & (df_retained['age'] <= 35), 'age_group'] = '26 - 35'
df_retained.loc[(df_retained['age'] >= 36) & (df_retained['age'] <= 45), 'age_group'] = '36 - 45'
df_retained.loc[(df_retained['age'] >= 46) & (df_retained['age'] <= 55), 'age_group'] = '46 - 55'
df_retained.loc[(df_retained['age'] >= 56) & (df_retained['age'] <= 65), 'age_group'] = '56 - 65'
df_retained.loc[(df_retained['age'] >= 66) & (df_retained['age'] <= 75), 'age_group'] = '66 - 75'
df_retained.loc[(df_retained['age'] >= 77) & (df_retained['age'] <= 85), 'age_group'] = '76 - 85'

### Crosstabs:
fam_dep= pd.crosstab(df_retained['marital_status'], df_retained['goods_category'], dropna = False)
loy_reg = pd.crosstab(df_retained['region'], df_retained['loyalty_flag'], dropna = False)

### creating a "family_status" column
df_retained.loc[(df_retained['dependants'] == 0), 'family_status'] = 'single'
df_retained.loc[(df_retained['dependants'] >= 1), 'family_status'] = 'family'



## Note: Instacart is a real company that’s made their data available online. However, the contents of this project brief have been fabricated for the purpose of this student project.


