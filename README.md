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

![Screen Shot 2022-04-03 at 8 25 44 PM](https://user-images.githubusercontent.com/90650209/161455819-49d12773-5147-44c0-a449-9a66a4bdd8b5.png)


# New Top Schools
top_schools = per_school_summary_df.sort_values(["% Overall Passing"], ascending = False)

![Screen Shot 2022-04-03 at 8 24 20 PM](https://user-images.githubusercontent.com/90650209/161455725-a0a7e356-cdaf-48ef-9b2a-fc83f1863f17.png)


It remains the same.
As well as the bottom schools

# Spending Per Student 
<img width="804" alt="Screen Shot 2022-04-03 at 8 27 57 PM" src="https://user-images.githubusercontent.com/90650209/161455951-555eec1d-760b-4b5d-9fcd-86048f9305a8.png">

# New Spending Per Student
![Screen Shot 2022-04-03 at 8 22 17 PM](https://user-images.githubusercontent.com/90650209/161455647-ac51e910-fb2c-44e0-b4f0-1cc1a9f40492.png)

There is a increase in overall passing grade of 9% when the students are dropped. There are increases across the board in the 585-615 range. 

# Size of School

All averages by size of school remained the same

<img width="752" alt="Screen Shot 2022-04-03 at 8 34 41 PM" src="https://user-images.githubusercontent.com/90650209/161456331-4bc0afdb-fe87-421c-ae51-a7e032f0b439.png">


<img width="782" alt="Screen Shot 2022-04-03 at 8 32 38 PM" src="https://user-images.githubusercontent.com/90650209/161456210-15568483-9418-490b-be64-3bd75fa57261.png">

# School Type

The Averages stayed the same between the different data types

<img width="752" alt="Screen Shot 2022-04-03 at 8 37 28 PM" src="https://user-images.githubusercontent.com/90650209/161456457-dde136d0-a5b0-4761-b078-d28c6839d52e.png">


<img width="748" alt="Screen Shot 2022-04-03 at 8 36 50 PM" src="https://user-images.githubusercontent.com/90650209/161456420-0bd1b893-9d30-4e33-b855-7efeb127ab6c.png">
