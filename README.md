# School District Analysis

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
*insert 4 screen shots*
The scores by grade is the most obviously changed DataFrame. The overall averages per school are only subtly changed by the removal of THS 9th grade (which tells me that and is supported by the scores by grade for THS that each grade performed similarly), but looking at the grades in each school makes the removal of the 9th grade THS scores obvious. Their cell is replaced by a NaN, or "Not a Number". It's a clear reminder that I removed that data, which is why a disclaimer about the removal of that data is necessary. If a school board member looked at my updated data without the disclaimer, they would be confused. 
* Scores by Spend 
There is no statistically significant difference in these two dataframes. By grouping the grades into schools, and the schools into a larger group, the number of students' whos grades were removed have become so small in THS's spend category, that it takes far more significant figures to notice a change than what I'm presenting to the school board. 
*insert 2 screen grabs*
* Scores by School Size
The same reasoning applies to these DataFrames as well. There are even fewer groups, so the removed students cause an even smaller percent change. To the school board, this data remains unchanged. 
*insert 2 screen grabs*
* Scores by School Type
With only two types of school, the previous reasoning for a lack of change is even more true. The analysis of scores by school type was not significantly changed by eliminating a set of potentially manipulated grades. The overall trends still hold true. 
*insert 2 screen grabs*

## Summary 

Overall, the removal of data most greatly changed the data that focused on how the individual schools performed. The district summary showed a change in total students counted, the school summary was changed with the THS line having fewer students, and the statistics being reduced, THS was nearly bumped to a lower performance rank, and the per grade math and reading scores listed NaN under THS 9th grade. 

I don't think this change should dramatically change how the district school board interacts with this data. The main overall trends of how school size, per student spending, and type of school remained unchanged, and I personally think those DataFrames show better information to make overall decisions on how to allocate money for the next year, which was the original mission of this data analysis 
