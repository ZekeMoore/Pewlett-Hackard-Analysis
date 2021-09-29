# Pewlett-Hackard-Analysis

## Purpose

The purpose of this analysis was to learn how to design the data base and create Entity Relationship Diagram, to design and manage tables and write basic to intermidiate SQL statements. Postgres and pgAdmin software was used for this project.

The data was presented in several .scv files. The relationship diagram was built in [QuickDBD](https://www.quickdatabasediagrams.com/). Then csvs were imported to pgAdmin, the database was created and later queries were made to receive needed information.


## Results

As a final result, two tables were created: Mentorship Eligibility (the list of employees who are eligible to participate in a mentorship program linked to the job title) and Retiring Titles (the number of retiring employees per job title).

The major findings as follows:

Retiring Titles Table 

![retiring_titles](https://github.com/ZekeMoore/Pewlett-Hackard-Analysis/blob/1fc50043816c9167a34094461e6b5f73d14f4c8d/Pewlett-Hackard-Analysis%20Folder/Resources/retiring_titles.png)

* Retiring Titles table provides the information about how many employees are going to retire per job title. Company may think about balancing the age of employees in the future to avoid mass retirements.

* Also, according to the Retirement Titles company can see that the majority of all future retired employees take senior positions which is potentially dangerous. Company may think more about training staff on lower positions to take senior positions in the future.

Mentorship Eligibility Table

![mentorship_eligibility](https://github.com/ZekeMoore/Pewlett-Hackard-Analysis/blob/2e34b87986253396ce753aa360f332210b736dba/Pewlett-Hackard-Analysis%20Folder/Resources/retirement_eligibility.png)

* Mentorship Eligibility gives the information about current job title of those who retire soon. It means that company can see the positions which will be free in the future.

* Also, from the Mentorship Eligibility the company can see the order of positions which will be free soon. Based on this information HR can set the priorities and plan the hiring in advance.


## Summary

In the end, there are two questions which answers may provide additional insight:

1) How many roles will need to be filled as the "silver tsunami" begins to make an impact?

The number many people who are about to retire is 90398. 
This number can be retrieved form Retiring Titles table using the query:
```
SELECT SUM(count) 
FROM retiring_titles;
```

2) Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?

There are 1549 employees who are ready to mentor the next generation, which shows that with help of quality management there is enough people to perform the task.
This number can be retrieved from Mentorship Eligibility table using the query:
```
SELECT COUNT(first_name)
FROM mentorship_eligibility;
```
