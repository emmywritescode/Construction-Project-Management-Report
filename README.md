# A Construction Project Management Report
![](image.jpg)
## Introduction
This is a Power BI project on a simple data set from a number of construction sites generated from project management field apps that are used for quality, safety and site management. The data analyzed here is depicted as "Tasks" - is an action item typically used for quality snags/defects or safety issues. The goal of the project is to understand how improvements in efficiency, cost savings, safety, etc  can be made in the building construction management process, leveraging the huge amounts of data generated.
## Problem statement
The Project Manager wants to understand the tasks peculiarities of the projects currently being managed. Among what he wants to determine are:
- Task group associated with the majority of tasks.
- Resolution time by task groups.
- Task status change time.
- Task causes and task priority.
## Skills demonstrated
The following Power BI skills were incorporated into this project:
- Data cleaning and transformation using Power Query Editor.
- Knowledge of DAX and measures (CALCULATE, COUNT, COUNTROWS, DISTINCTCOUNT, AVERAGE)
- M Query and custom columns using (IF, ELSE, THEN).
- Data visualization on Power BI.
## Data sourcing
This data set was obtained from Kaggle. It was donated by Jason Rymer, a BIM Manager from Ireland who was keen to see more construction-related data online to be used to learn. This [link](https://www.kaggle.com/datasets/claytonmiller/construction-and-project-management-example-data) provides access to the data.
## Data cleaning & transformation
The CSV file loaded into Power BI features 19 columns and 12,424 rows of data. Kaggle contributor @kscoder77 provided the data dictionary, which provided the context for this analysis. Here is a [link](https://www.kaggle.com/code/kscoder77/construction-project-data-analysis) to her helpful contribution.

Firstly, exploratory data analysis was done to have a quick and sufficient understanding of the data.

Secondly, the 'Priority' column had over 10K missing data, meaning that dropping the rows will lead to a significant loss of data. It was observed that 'Behavioral Failure' accounted for majority of the entries in this column, and the usual corresponding value in the 'Task Group' column was 'Safety'. Therefore, a custom column was created to check that when 'Priority' is null and 'Task Group' is 'Safety', the column is updated to 'Behavioral Failure'. Another condition checks that when 'Priority' is null and 'Task group' is not 'safety', then 'Priority' updates to 'Other'. This was done with M Query in the Power Query Editor interface.

Thirdly, it was observed from the 'Type' column that the tasks with null entries in the 'To Package' column are related to design. Therefore, all null values were replaced with 'Design'.

Additionally, columns like 'Target', 'Association', 'Cause', Task Group, 'Images', 'Commits', and 'Documents' with vast amount of missing or null entries were replaced with their most assigned or modal values respectively, as observed on individual columns. This is because there was no indication as to the likely values that could replace the missing data.

Lastly, an additional column, 'Days Taken to Complete Task' was created. This simply is a methematical subtraction of the two date columns: Created and Status Changed.

## Analysis and Visualization




