# 2.07 Activity 1

Keep working on the `bank` database.

1. In the `loan` table (which is part of the `bank` database), there's column status A, B, C, and D. Using the `case` statement we will create a new column, named status_desc, with the values there with a brief description:

    - 'A' : 'Good - Contract Finished'
    - 'B' : 'Defaulter - Contract Finished'
    - 'C' : 'Good - Contract Running'
    - 'D' : 'In Debt - Contract Running'


2. In the lesson, we talked about the reasons why normalization is critical in a database design. One of the reasons we talked about was data anomalies. We will discuss data anomalies in more detail in the next lesson. Here are a couple of resources that you can use to read more about data anomalies. Go through these links and then we will have a discussion in class:

    - https://beginnersbook.com/2015/05/normalization-in-dbms/
    - https://databasemanagement.fandom.com/wiki/Data_Anomalies


# 2.07 Activity 2

1. What could be possible anomalies in a table?

2. In the class, we looked at an example where the problem statement was -> "What is the average loan amount taken by customers in each of the status categories?     Arrange them from highest to lowest"
  The query is shown below: 

    ```sql
    select avg(amount) as Average, status from bank.loan
    group by Status
    order by Average asc;
    ```
  
    Your objective is to find the **maximum** and the **minimum** in each `Status` category. 
  

  # 2.07 Activity 3

In this activity, we will be using the `bank` database.

1. Find out how many cards of each type have been issued.
2. Find out how many customers there are by the district.
3. Find out average transaction amount by type.
4. In the query shown below, there are several rows returned. But there a few places where the column `k_symbol` is an empty string. Your task it to use a filter to remove those rows of data. After the filter gets applied, you would see that the number of rows have reduced.

    ```sql
    select type, operation, k_symbol, round(avg(balance),2)
    from bank.trans
    group by type, operation, k_symbol
    order by type, operation, k_symbol;
    ```

You will see that there is still one row where the column operation is having blank value. This is because there is no corresponding value for operation where there is a value for type and k_symbol and we have placed a filter only on k_symbol.


# 2.07 Activity 4

Keep using the `bank` database.

1. Find the districts with more than 100 clients.
2. Find the transactions with a mean amount greater than 10000 grouped by type and operation.