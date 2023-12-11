### Multiple Distribution Analysis

In this project, I analyse a data set of students with information about their teachers and test scores across 5 years. In this data set, there are certain teachers which cheat by increasing their student's test scores. I used data analysis and statistical methods to figure out which teachers were cheating and which teachers were honest.

I created a video which explains the process of this project: https://youtu.be/usvZqmSxeGA

To run the code, import the .Rmd and .csv files into the same directory and run.

#### Data Set
Each row in the ChildrenScores.csv data set represents a single student. The column teacherYX represents the teacher the student had in year X, while scoreYX represents the score that the student got in year X. The meanScore column is the average score of all 5 years for that student. The code for each teacher is unique, so teacher Y3.001 ≠ teacher Y4.001. In this situation, cohot is irrelevant.

#### Methodology
There are some key points about this data set which determine how we tackle the problem. Firstly, the intelligence of students in each class is random and so majority of classes have a normal distribution of smartness when it comes to students. This means that we cannot compare the students with other students in their same class, as we cannot expect all students to have similar test scores. Rather, we must separate the data into each class taught by each unique teacher, and compare the test scores for that teachers class with the test scores the students got in their other classes. 

To do this, we found a residual value by subtracting the score a student got for a particular class with the average of their other scores in the other 4 years. This results in a clear divide between the residuals of cheating and honest teachers.

Now that we know the cheating eachers, we can take a closer look at the data. We observe that the honest teachers residuals have a normal distribution, while the cheating teachers have a strange looking distribution. This is because the cheating teachers only altered the scores of some of their students, thus a portion of their scores have the same distribution as the honest scores. Using the maximum likelihood estimator from the DIY regression modelling repository, we extrapolated the mean and standard deviation of cheating scores.

#### Conclusion
We would expect that the cheating teachers alter around 77.1% of their student's scores.
