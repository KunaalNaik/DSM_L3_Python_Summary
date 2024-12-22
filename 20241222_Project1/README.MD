### Markdown Documentation: Data Summary Code

---

#### **Step 1: Import Data**

**Description:**
Load the dataset into a pandas DataFrame and inspect its structure to understand the columns, data types, and memory usage.

```python
import pandas as pd

# Load data from Excel file
df = pd.read_excel('2 Sample - Superstore.xlsx', sheet_name='Orders')

# Display dataset information
df.info()
```

---

#### **Step 2: Create Segment Summary**

**Description:**
Group the data by the "Segment" column and calculate the total sales for each segment. Reset the index to create a clean DataFrame.

##### **Manual Approach:**
```python
# Group by 'Segment' and calculate the sum of 'Sales'
df_segment_summ = df.groupby('Segment')['Sales'].sum()

# Reset index to convert to DataFrame
df_segment = df_segment_summ.reset_index()
df_segment.columns = ['Dimension', 'Value_Sales']
```

##### **Optimized Approach:**
```python
# Combine grouping and renaming steps
df_segment_summ = df.groupby('Segment')['Sales'].sum().reset_index()
df_segment_summ.columns = ['Dimension', 'Value_Sales']
```

---

#### **Step 3: Create Region Summary**

**Description:**
Group the data by the "Region" column and calculate the total sales for each region. Reset the index and rename the columns.

```python
# Group by 'Region' and calculate the sum of 'Sales'
df_region_summ = df.groupby('Region')['Sales'].sum().reset_index()
df_region_summ.columns = ['Dimension', 'Value_Sales']
```

---

#### **Step 4: Create Category Summary**

**Description:**
Group the data by the "Category" column and calculate the total sales for each category. Reset the index and rename the columns.

```python
# Group by 'Category' and calculate the sum of 'Sales'
df_category_summ = df.groupby('Category')['Sales'].sum().reset_index()
df_category_summ.columns = ['Dimension', 'Value_Sales']
```

---

#### **Step 5: Create Sub-Category Summary**

**Description:**
Group the data by the "Sub-Category" column and calculate the total sales for each sub-category. Reset the index and rename the columns.

```python
# Group by 'Sub-Category' and calculate the sum of 'Sales'
df_sub_category_summ = df.groupby('Sub-Category')['Sales'].sum().reset_index()
df_sub_category_summ.columns = ['Dimension', 'Value_Sales']
```

---

#### **Step 6: Concatenate Summaries**

**Description:**
Combine the summaries for Segment, Region, Category, and Sub-Category into a single DataFrame using `pd.concat()`.

```python
# Concatenate all summaries into a single DataFrame
df_summary = pd.concat([df_segment_summ, df_region_summ, df_category_summ, df_sub_category_summ], axis=0)
```

---

#### **Step 7: Loop Through Dimensions**

**Description:**
Automate the summary creation process for multiple dimensions (Segment, Region, Category, Sub-Category) using a loop. Append each summary to a combined DataFrame.

```python
dimensions = ['Segment', 'Region', 'Category', 'Sub-Category']
df_summary = pd.DataFrame(columns=['Dimension', 'Value_Sales'])

# Loop through dimensions to generate summaries
for dim in dimensions:
    df_result = df.groupby(dim)['Sales'].sum().reset_index()
    df_result.columns = ['Dimension', 'Value_Sales']
    df_summary = pd.concat([df_summary, df_result], axis=0)
```

---

#### **Step 8: User-Defined Function**

**Description:**
Create a reusable function that generates a summary for a given list of dimensions. This function takes a DataFrame and a list of column names as inputs and returns a combined summary DataFrame.

```python
# Define a function to create summaries for any dimensions
def create_summary(input_df, dimensions):
    df_summary = pd.DataFrame(columns=['Dimension', 'Value_Sales'])
    for dim in dimensions:
        df_result = input_df.groupby(dim)['Sales'].sum().reset_index()
        df_result.columns = ['Dimension', 'Value_Sales']
        df_summary = pd.concat([df_summary, df_result], axis=0)
    return df_summary

# Generate summary for specified dimensions
result_summary = create_summary(df, ['Segment', 'Region', 'Category'])
```

---

### Key Takeaways
1. Use **groupby()** to summarize data by different dimensions.
2. Apply **reset_index()** to convert grouped results into DataFrames.
3. Combine summaries with **pd.concat()** for a consolidated view.
4. Wrap logic in functions for reusability and scalability.

