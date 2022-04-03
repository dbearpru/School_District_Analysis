# School_District_Analysis
School District analysis with python

Purpose:

The purpose of this analysis is to find the differences in performance on standardized scores in math and reading scores. I had to find the total amount of students and overall_passing_percentage.
I categorized the schools by spending per student, size of school, and type of school. I also determined the top performing schools in the district.  
The wrinkle that was thrown was the 9th grade class of Thomas High school being accused of cheating. We then had to find the changes in the numbers affected by the cheating class. 

Results:

# Orignal Student Count

I calculated the original student count by doing a count function on the "Student ID" column.
student_count = school_data_complete_df["Student ID"].count()
student_count

39170

ninth_grade_thomas_count = len(school_data_complete_df.loc[(student_data_df["school_name"]== "Thomas High School")
                    & (student_data_df["grade"]== "9th")])

# New Student Count

First we calculated the overall total and then calculated the total from the 9th grade class of Thomas High.
Once that was accomplished we subtracted it from the total to get a new total of 38709.

Get the total student count 

student_count = school_data_complete_df["Student ID"].count()
Step 2. Subtract the number of students that are in ninth grade at 
Thomas High School from the total student count to get the new total student count.
new_student_count = (student_count - ninth_grade_thomas_count)

new_student_count

38709

# Overall Passing Percentage

First we had to calculate the determine the amount of children that had passed both math and reading with:

passing_math_reading = school_data_complete_df[(school_data_complete_df["math_score"] >= 70) & (school_data_complete_df["reading_score"] >= 70)]

65.2

# New Overall Passing Percentage

Then with the new student count we got previous we divide to get the new overall passing grade. 
overall_passing_percentage = overall_passing_math_reading_count/ new_student_count *100
64.9

Only a .3 percent drop after Thomas 9th graders where removed. 

# Top School

The top Schools go in this order.
top_schools = per_school_summary_df.sort_values(["% Overall Passing"], ascending=False)

Cabrera
Thomas
Griffin
Wilson
Pena

# New Top Schools
top_schools = per_school_summary_df.sort_values(["% Overall Passing"], ascending = False)

Cabrera
Thomas
Griffin
Wilson
Pena

It remains the same.
As well as the bottom schools

# Spending Per Student 



There is a statement summarizing four changes to the school district analysis after reading and math scores have been replaced (5 pt).
