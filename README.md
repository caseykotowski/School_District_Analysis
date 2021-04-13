# School_District_Analysis

## Purpose
A school district wanted to analyze the data from recent math and reading tests across all high schools in the district to determine budget allocation for the next year. The high schools are grade 9-12, and there is a mix of charter and standard district schools. I had access to data per student (test grades and school grade), as well as per school (size, budget, and type). 

It was my job to take this information and organize it, as well as take some calculations to show the district office how the schools are performing by grade, budget per student, size, and school type. 

There was a small issue, and there were reasons to suspect that the 9th grade class at Thomas high school had some manipulated grades in the system. This was discovered after the full analysis was completed, so I had to go back and remove all of that grade's data just to make sure the cheating did not affect the district's decisions. Due to these changes, a large part of the results will focus on how removing that school's 9th graders changes the overall performance of the school and how it stacks up to the rest of the district. 

## Results

* District Summary
The district summary DataFrame includes the following columns 
```district_summary_df = pd.DataFrame(
        [{"Total Schools": school_count,
         "Total Students": student_count,
         "Total Budget": total_budget,
         "Average Math Score": average_math_score,
         "Average Reading Score": average_reading_score,
         "% Passing Math": passing_math_percentage,
         "% Passing Reading": passing_reading_percentage,
         "% Overall Passing": overall_passing_percentage}])
 ```
 The original output is:
 *Insert screen grab of df*
 When Thomas HS grade 9 is removed, the output is now:
 *Insert updated screen grab*
 The change in averages and percent passing are subtle, but noticable. There was a difference of a tenth of a point and a tenth of a percent in each category. Removing the scores for the Thomas HS 9th grade class didn't cause more of a change because overall, there are few of them in the district
* School Summary
The per school summary takes the same columns as the district summary, but breaks the data down per school. All grades are counted. 
```district_summary_df = pd.DataFrame(
          [{"Total Schools": school_count, 
          "Total Students": total_student_count, 
          "Total Budget": total_budget,
          "Average Math Score": average_math_score, 
          "Average Reading Score": average_reading_score,
          "% Passing Math": passing_math_percentage,
         "% Passing Reading": passing_reading_percentage,
        "% Overall Passing": overall_passing_percentage}])
```
*insert screen grab of original per school summary*
*insert screen grab of new per school summary*

* School Ranking
*insert two screen grabs*
Thomas High School's rank is not changed. It remains the second best performing school in the district, but the margins are changed. Griffen HS is now less than a tenth of a percentage away from over taking THS's spot. 
* Scores by Grade
*insert 2 screen shots*
* Scores by Spend 
*insert 2 screen grabs*
* Scores by School Size
*insert 2 screen grabs*
* Scores by School Type
*insert 2 screen grabs*

## Summary 
