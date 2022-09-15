# tanvir protfolio
import pandas as pd
raw_csv_data = pd.read_csv('Absenteeism_data.csv')

raw_csv_data

df = raw_csv_data.copy()

df

pd.options.display.max_columns = None
pd.options.display.max_rows = None
display(df)

df.info()

df.drop(['ID'], axis=1)

df['Age']

df['Age'].max()

df['Age'].min()

df['Age'].unique()

len(df['Age'].unique())

sorted(df['Age'].unique())

df_no_age = df.drop(['Age'], axis=1)

df_no_age

age_columns = pd.get_dummies(df['Age'])
age_columns

age_columns['check'] = age_columns.sum(axis=1)

age_columns

age_columns['check'].sum(axis=0)

age_columns

age_columns['check'].unique()

age_columns = age_columns.drop(['check'],axis=1)

age_columns

age_dummies = pd.get_dummies(df['Age'])

age_dummies

age_dummies = pd.get_dummies(df['Age'], drop_first = True)
age_dummies

##group the Age column

df.columns.values

age_columns.columns.values

df = df.drop(['Age'], axis=1)
df

age_columns.loc[:, 28:37]

age_columns.loc[:, 28:37].max(axis=1)

age_type_1 = age_columns.loc[:, 28:37].max(axis=1)
age_type_2 = age_columns.loc[:, 38:40].max(axis=1)
age_type_3 = age_columns.loc[:, 41:46].max(axis=1)
age_type_4 = age_columns.loc[:, 47:].max(axis=1)

age_type_2

df = pd.concat([df, age_type_1, age_type_2, age_type_3, age_type_4], axis=1)
df

df.columns.values

column_name = ['ID', 'Reason for Absence', 'Date', 'Transportation Expense',
       'Distance to Work', 'Daily Work Load Average', 'Body Mass Index',
       'Education', 'Children', 'Pets', 'Absenteeism Time in Hours', 'Age_1', 'Age_2',
       'Age_3', 'Age_4']

df.columns = column_name

df.columns

df.head()

df_concatenated = pd.concat([df_no_age, age_dummies], axis=1)

df_concatenated

df_concatenated.columns.values

column_names = ['ID', 'Reason for Absence', 'Date', 'Transportation Expense',
       'Distance to Work', 'Daily Work Load Average', 'Body Mass Index',
       'Education', 'Children', 'Pets', 28,
       29, 30, 31, 32, 33, 34, 36, 37, 38, 39, 40, 41, 43, 46, 47, 48, 49,
       50, 58, 'Absenteeism Time in Hours']

df_concatenated = df_concatenated[column_names]

df_concatenated

df_checkpoint_mod = df_concatenated.copy()

df_checkpoint_mod

