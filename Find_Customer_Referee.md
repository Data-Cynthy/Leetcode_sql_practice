##Problem Summary
You are given a table with customer information, where:
-id is the unique customer ID (primary key),
-name is the customer's name,
-referee_id is the ID of the person who referred them (can be NULL if they were not referred).

#Goal
Write an SQL query to return the names of customers who are either:
-Referred by a customer whose id is not equal to 2, OR
-Not referred by anyone (i.e., referee_id IS NULL).

#Table Schema
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| id          | int     |
| name        | varchar |
| referee_id  | int     |
+-------------+---------+

#Query Solution
SELECT name 
FROM Customer 
WHERE referee_id != 2 OR referee_id IS NULL

#Output
| name |
| ---- |
| Will |
| Jane |
| Bill |
| Zack |

#Explanation
-We want to exclude customers referred by the customer with ID = 2
-But also include customers who weren't referred by anyone (referee_id IS NULL)
-A simple OR condition helps cover both cases in one query, therefore:
-referee_id != 2: This filters out customers who were referred by customer with ID 2.
-referee_id IS NULL: Includes customers who were not referred by anyone.
-The OR condition ensures we capture both valid categories.

#SQL Concepts Used
SELECT & WHERE clause
OR logic operator
NULL value handling

#Links
[LeetCode Problem Link] (https://leetcode.com/problems/find-customer-referee/)
