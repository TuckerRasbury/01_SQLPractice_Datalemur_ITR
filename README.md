# Practicing SQL w/ Isaac D. Tucker-Rasbury via DataLemur
Using this as a space to log and organize my SQL practice using the website [DataLemur](https://datalemur.com). Hope you can learn something from this space as well!

## About this Repository
Being a data analyst means keeping my skills sharp. Herein, I log my SQL queries that I've been practicing while going through the exercises on DataLemur.com, a relatively new website where anyone can practice their SQL using questions from the prominent book "How to Ace the Data Science Interview". Some of these entries will have a accompanying LinkedIn posts and commentary, and I hope you follow those links and learn from the community commenting on those posts as you read along. Given this site has 50-70 questions and that I am doing these at my leisure, this repository will be updated as I go through them, ie. will be updated over time at my leisure.

Thanks for visiting my portfolio!

## Disclosure
The questions represented herein are from "How to Ace the Data Science Interview". The reproduction of questions here is not a statement of ownership, creation, or done for or with the intent for profit. This is an educational exercise intended to demonstrate my commitment to learning more about the tools used in the analytics industry. The full question along with data dictionaries can be located on the Datalemur site and have not been consistently, if at all reproduced, here for the author's convenience.

If you have any questions or concerns feel free to get in touch with me on LinkedIn.

## How the entries are logged
 - Question Title | Difficulty | Company Question is From | Date Completed
 - Question 
 - Code Answer
 - Number of Tries
 - Lessons learned, new skills practiced, and notable failures
 - LinkedIn posts about respective question, if applicable

## Table of Contents

### Easy Questions
- Working Entry [LinkedIn Power Creators (Part 1) | Easy | LinkedIn | 11/10/2022]()
- [Laptop Vs Mobile Viewership | Easy | New York Times | 10/17/2022](https://github.com/TuckerRasbury/SQLPractice_Datalemur_ITR/blob/main/README.md#laptop-vs-mobile-viewership--easy--new-york-times--10172022)
- [Data Science Skills | Easy | LinkedIn | 10/12/2022](https://github.com/TuckerRasbury/SQLPractice_Datalemur_ITR#data-science-skills--easy--linkedin--10122022)
- [Pages with No Likes | Easy | Facebook | 9/13/2022](https://github.com/TuckerRasbury/SQLPractice_Datalemur_ITR#pages-with-no-likes--easy--facebook--9132022)
- [Cities with Completed Trades | Easy | Robinhood | 9/12/2022](https://github.com/TuckerRasbury/SQLPractice_Datalemur_ITR#cities-with-completed-trades--easy--robinhood--9122022)

### Medium
- [Placeholder]()

### Hard
- [Placeholder]()
 
## Question Responses
_Note: Questions ordered by most recent date._

### LinkedIn Power Creators (Part 1) | Easy | LinkedIn | 11/10/2022
- Question: Write a query to return the IDs of these LinkedIn power creators ordered by the IDs.

````
-- Write a query to return the IDs of these
-- LinkedIn power creators ordered by the IDs.

SELECT
  profile_id,
  -- personal_profiles.employer_id,
  personal_profiles.followers AS Personal_Followers,
  -- company_pages.company_id,
  company_pages.followers AS Company_Followers
FROM personal_profiles
JOIN company_pages ON company_pages.company_id = personal_profiles.employer_ID;
````

![Image](Path)

- Number of Tries:
- Lessons Learned: 
- LinkedIn Post: [Here]()

### Laptop Vs Mobile Viewership | Easy | New York Times | 10/17/2022
- Question: Assume that you are given a table containing information on viewership by device type (where the three types are laptop, tablet, and phone). Define “mobile” as the sum of tablet and phone viewership numbers. **Write a query to compare the viewership on laptops versus mobile devices. Output the total viewership for laptop and mobile devices in the format of "laptop_views" and "mobile_views".**


![Image](images/Laptop_Vs_Mobile_Viewership/Snap.png)
[Screenshot of submission](https://github.com/TuckerRasbury/SQLPractice_Datalemur_ITR/blob/c524a6a0fbce1630dc2e778bd1184ebb7165637b/images/Laptop_Vs_Mobile_Viewership/Screen%20Shot%202022-10-17%20at%208.34.36%20PM.png)

- Number of Tries: 1
- Lessons Learned: Building a plan for your query is essential. This is one of the more difficult queries I've written using CASE statements, but the odd thing is that I felt really comfortable writing it! Took a few tries to get the syntax right, but I really enjoyed writing this.
- LinkedIn Post: [Here]()


### Data Science Skills | Easy | LinkedIn | 10/12/2022
- Question: Given a table of candidates and their skills, you're tasked with finding the candidates best suited for an open Data Science job. You want to find candidates who are proficient in Python, Tableau, and PostgreSQL. **Write a SQL query to list the candidates who possess all of the required skills for the job. Sort the the output by candidate ID in ascending order.**

![Image](images/Data_Science_Skills/carbon.png)

- Number of Tries: 2
- Lessons Learned: I learned about and practiced using the IN function with the WHERE subclause. The IN function is fairly new to me.
- LinkedIn Post: [Here](https://www.linkedin.com/posts/tuckerrasbury_dataanalyst-sql-growthmindset-activity-6985986546453622784-alHY?utm_source=share&utm_medium=member_desktop)


### Pages with No Likes | Easy | Facebook | 9/13/2022
- Question: Assume you are given the tables below about Facebook pages and page likes. **Write a query to return the page IDs of all the Facebook pages that don't have any likes. The output should be in ascending order.**

```
-- Code Answer Submitted
SELECT
  pages.page_id
FROM pages
LEFT JOIN page_likes
ON pages.page_id = page_likes.page_id
GROUP{ BY pages.page_id
HAVING Count(page_likes.page_id) < 1;
```

[Link to screenshot here](https://github.com/TuckerRasbury/SQLPractice_Datalemur_ITR/blob/4f19b8b6a8fe92d54f98f3bc3514d8178cccd09f/images/pages_with_no_likes/1663078588840.jpeg)

- Number of Tries: 2
- Lessons Learned: HAVING vs WHERE 

“A HAVING clause is like a WHERE clause, but applies only to groups as a whole (that is, to the rows in the result set representing groups), whereas the WHERE clause applies to individual rows. A query can contain both a WHERE clause and a HAVING clause.” [🔗 Microsoft Documentation Link  🔗](https://learn.microsoft.com/en-us/sql/ssms/visual-db-tools/use-having-and-where-clauses-in-the-same-query-visual-database-tools?view=sql-server-ver16#:~:text=A%20HAVING%20clause%20is%20like,clause%20and%20a%20HAVING%20clause)

This one was more challenging for me since I am generally used to painting in broad strokes. Both clauses allow you to filter the broader dataset. The trick-for me at least is that they do the same thing BUT UNDER DIFFERENT circumstances! I tried to answer the question with both because I refused to accept the difference, but ultimately landed back where I started, ie. the difference between these functions is substantive and they are not interchangeable.
- LinkedIn Post: [Here](https://www.linkedin.com/posts/tuckerrasbury_datalemur-sql-analytics-activity-6975457181575835649-6wxE?utm_source=share&utm_medium=member_desktop)


### Cities with Completed Trades | Easy | Robinhood | 9/12/2022
- Question: You are given the tables below containing information on Robinhood trades and users. **Write a query to list the top three cities that have the most completed trade orders in descending order.**


```
-- Code Answer Submitted
SELECT
  users.city,
  COUNT(order_id) AS total_orders
FROM users
JOIN trades
ON users.user_id = trades.user_id
WHERE status = 'Completed'
GROUP BY city
ORDER BY total_orders DESC
LIMIT 3
```

[Link to screenshot here](Path)

- Number of Tries: 1
- Lessons Learned: SQL has an order of operations - I tend to familiarize myself with the data and then draft a query plan before testing code. Finally, I’ll fill in pieces as I go. But, this question required so many components that I had to double check my basics and I realized that the order of operations was far from a locked in skill for me. 
- LinkedIn Post: [Here](https://www.linkedin.com/posts/tuckerrasbury_dataanalytics-sql-datalemur-activity-6975117717653655552-KgbQ?utm_source=share&utm_medium=member_desktop)

## Appendix

**Template**

### Title | Difficulty | Company | Date
- Question: 

![Image](Path)

- Number of Tries:
- Lessons Learned: 
- LinkedIn Post: [Here]()

## Process for Updating Readme
1. Answer a question on Datalemur.com 
2. Copy the template from the appendix to the top of the questions answered section.
3. Fill in the spaces of the template in the new entry as you go or after the question is answered on the platform.
4. Create an image folder titled with the name of the question.
5. Place whatever screenshots or code shots made using [Carbon](https://carbon.now.sh) into the image folder to fill in the image space. This space can be purely functional (ie. easy screenshot and go) or a place for creativity (ie. using Carbon to create a beautiful representation of SQL). Pick based on time, energy, and taste.
6. Update the Table of Contents to ensure question responses are easy to navigate.
7. Do your best to talk about the work on LinkedIn or Medium.
