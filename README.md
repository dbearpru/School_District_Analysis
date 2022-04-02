# School_District_Analysis
School District analysis with python

Purpose:
The purpose of the analysis was to run an analysis on the scores for different schools based school spending, school size, and school type. There is an added wrinkle of of academic dishonesty affecting the 9th grade in Thomas High School. 

Results

Fixing the Data to account for the academic issues at Thomas High School.
The first thing we have to do is remove the whole 9th grade class by replacing all there math and reading scores with NaN. 
It takes out their scores out of the averages. We will later average scores for our final analysis. 

student_data_df.loc[(student_data_df["school_name"]== "Thomas High School") 
                    & (student_data_df["grade"]== "9th"), "reading_score"] = np.nan
		    
student_data_df.loc[(student_data_df["school_name"]== "Thomas High School")
                    & (student_data_df["grade"]== "9th"), "math_score"] = np.nan
		    
Total Schools	Total Students	Total Budget	Average Math Score	Average Reading Score	% Passing Math	% Passing Reading	% Overall Passing
0	15	39,170	$24,649,428.00	78.9	81.9	74.8	85.7	64.9

	
0	15	39170 student_name 39170 ...	24649428	78.985371	81.87784	65.17

Replacing the scores from Thomas dragged there averages down slighty only .2 percent in the case of overall score.
Overall it doesn't change much. It is a drop in the bucket compared to all the other students in all the other schools. 



