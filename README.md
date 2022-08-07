# Movies_Data_Analysis
This project is based on my online training
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
pd.options.display.max_columns = 30
pd.options.display.float_format = '{:.2}'.format

df=pd.read_csv("Data file location)
df
df.info()
df.genres[1]
df.cast[1]
df.describe()


df.hist(figsize=(20,15),bins=100)
plt.show()

df.budget_musd.value_counts(dropna = False).head(10)

df.vote_average.value_counts(dropna=False)

df.vote_count.value_counts()
df.describe(include="object")
df[df.title=="Cinderella"]

from IPython.display import HTML
df_best = df[["poster_path","title","budget_musd","revenue_musd","vote_count","vote_average","popularity"]].copy()
df_best
df_best["profit_musd"] = df.revenue_musd.sub(df.budget_musd)
df_best["return"] = df.revenue_musd.div(df.budget_musd)
df_best

df_best.columns = ["", "Title", "Budget", "Revenue", "Votes", "Average Rating", "Popularity", "Profit", "ROI"]
df_best
df_best.set_index ("Title", inplace = True)
df_best

