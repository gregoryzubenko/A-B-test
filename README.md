# A-B-test
During testing of one hypothesis, the target group was offered a new mechanism for paying for services on the site, while the control group retained the basic mechanics. As a task, you need to analyze the results of the experiment and decide whether it is worth launching a new payment mechanism for all users.

# 1. Input

You have 4 csv files as input:

groups.csv - file with information about the user's belonging to the control or experimental group (A - control, B - target group)
groups_add.csv - an additional file with users that was sent to you 2 days after the data transfer
active_studs.csv - a file with information about users who logged into the platform on the days of the experiment.
checks.csv - a file with information about user payments on the days of the experiment.
1.3 Questions

We invite you to answer the following questions:

What metrics do you look at during the analysis and why?
Are there differences in performance and what might they be related to?
Are these differences statistically significant?
Is it worth launching new mechanics for all users?
This list of questions is optional and you can use your own plan to answer.

# 2.SQL
2.1 Very diligent students.

2.1.1 Condition

Educational courses consist of various lessons, each of which consists of several small tasks. Each such small task is called a "pea".

Let's call a very diligent student a user who correctly solved 20 peas at least once during the current month.

2.1.2 Task

Given the default.peas table:

Attribute name Attribute type Meaning
st_id int Student ID
timest timestamp Card decision time
correct bool Is the pea solved correctly?
subject text The discipline the pea is in
It is necessary to write an optimal query that will give information about the number of very diligent students.

NB! By a diligent student, we mean a student who correctly solved 20 problems for the current month.

2.2 Funnel optimization

2.2.1 Condition

The educational platform offers students to take courses according to the trial model: a student can solve only 30 peas a day for free. For an unlimited number of tasks in a particular discipline, the student must purchase full access. The team ran an experiment where they tested the new payment screen.

2.2.2 Task

Table given: default.peas (see above), default.studs:

Attribute name Attribute type Meaning
st_id int Student ID
test_grp text The label of the student in this experiment
and default.final_project_check:

Attribute name Attribute type Meaning
st_id int Student ID
sale_time timestamp Purchase time
money int The price at which this course was purchased
subject text Discipline purchased with full access
It is necessary to upload the following information about user groups in one request:

-ARPU
-ARPAU
-CR in purchase
-CR of an active user per purchase
-User CR from math activity (subject = 'math') to math course purchase
-ARPU is calculated relative to all users in groups.

An active user is one who has solved more than 10 problems correctly in any discipline for the entire time.

A user who has solved 2 or more problems correctly in mathematics for the entire time is considered active in mathematics.

# Python
3.1 Challenge

Implement a function that will automatically load information from the additional file groups_add.csv (headers may differ) and recalculate metrics based on additional parameters.
Implement a function that will build graphs based on the received metrics.
