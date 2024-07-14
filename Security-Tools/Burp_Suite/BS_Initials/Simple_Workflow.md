# Initial Steps:

1. Download the Burpsuite Certificate: Open Browser goto `http://burp/` Download
2. Install the BS Certificate at Attcker VM: Firefox > Settings > search for `Certificate` > View Certificate > Inport > Install > Ok
3. Install `FoxyProxy Extention` from Firefox
4. Check Proxy Settings in BS: Proxy > Proxy Settings > By Deafult: `Http Proxy: 127.0.0.1 & Port: 8080`
5. Set up the Proxy in Browser: Firefox > Settings > search for `proxy` > Manual Proxy > `Http Proxy: 127.0.0.1 & Port: 8080` > Ok

> Use `http://demo.testfire.net/` for testing

# Steps to Tests:
1. Click on `Intercept is On` to get the traffic thu BS.
2. Click to `Sign In` on Site in Browser.
3. Capture the Packet in BS.
![image](https://github.com/user-attachments/assets/bc403516-19fb-40da-bd95-4515046071a0)

4. `Action` or `Right Click` to send it to any other Modules.
![image](https://github.com/user-attachments/assets/1d4e8362-f6ca-4a7e-ab8a-da89455c6442)

5. In Repeater:
- `Modify the Request` & analyse the Response as many time as required.
- `show the reponse in browser` if required
- `follow redirection` to open the same page if not succeed/failed.

6. In Intruder:
- `Fuzz/Brute Force` the Request's Parameters and Analyse the Response.
- Add the `positions` input fields to brute force.
![image](https://github.com/user-attachments/assets/8d23694d-28e4-4e1b-8f90-37820bc08110)

- Select the `Attack Type`
- Add values in the `list` in `Payloads`
![image](https://github.com/user-attachments/assets/dac6af5d-055b-4ee0-b1fd-de79042fc1eb)

- `Start the Attack`
- Analyse each Request's response by clicking on it.
- Failed Response:
![image](https://github.com/user-attachments/assets/798d7de0-7a19-471d-9a99-d5eb0bdb022a)

- Successful Response:
![image](https://github.com/user-attachments/assets/ee11e336-73d9-4dc9-a145-39f7c4f747dd)

- Show Response in Browser:
![image](https://github.com/user-attachments/assets/79dc40e0-674d-4e1e-8c8f-bb50bb6f864b)

- The Result:
![image](https://github.com/user-attachments/assets/39ab7654-1ce9-481b-8756-d984dd01dbdd)


