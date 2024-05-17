```python
import seaborn as sns

# load the dataset
glue = sns.load_dataset("glue")
glue

glue_df = sns.catplot(
data=glue,
kind ='bar',
x ='Task',
y ='Score',
hue ='Model',
col ='Year',
row ='Encoder',
height=3,
aspect =1.5,
palette='Set2')

# set labels
glue_df.set_axis_labels('Tasks', 'Scores')
glue_df
```
