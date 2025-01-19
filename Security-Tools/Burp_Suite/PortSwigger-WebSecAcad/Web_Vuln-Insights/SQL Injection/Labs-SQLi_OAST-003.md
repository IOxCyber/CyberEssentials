<div align="center">
  <h1>-------------------------- SQLi LABS 003 ---------------------------</h1>
</div>

# [CheatSheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)

## Lab 13: Blind SQL injection with time delays and information retrieval [Link](https://portswigger.net/web-security/sql-injection/blind/lab-time-delays-info-retrieval)
- Capture the GET request > Repeater > Modify the value of the cookies: TrackingId.
- Add `SELECT CASE WHEN (YOUR-CONDITION-HERE) THEN pg_sleep(10) ELSE pg_sleep(0) END--`
- Modify the Conditions & observe the delay in response.
- Check the PWD length in condition > Modify the query to get the pwd letters > Intruder > `SUBSTRING(password,1,1)='a'` # SUBSTRING(password,POSITION,No. OF CHARs)='a'
> You should see a column in the "result" called `Response received` for the time delay value.


## Lab 14: Blind SQL injection with out-of-band interaction [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-exploiting-blind-sql-injection-using-out-of-band-oast-techniques/sql-injection/blind/lab-out-of-band)


## Lab 15: Blind SQL injection with out-of-band data exfiltration [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-exploiting-blind-sql-injection-using-out-of-band-oast-techniques/sql-injection/blind/lab-out-of-band-data-exfiltration)


## Lab 16: [Link]()
