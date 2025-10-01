# 1. Brute Force -> Low Security Level

```
For More information ->https://owasp.org/www-community/attacks/Brute_force_attack
```
![alt text](images/1.png)

## Let's try with Burp Suite

![alt text](images/2.png)

### ``` Send it to intruder ```
-Add payload position to Username and Password
-Select cluster bom attack
![alt text](images/4.png)
![alt text](images/3.png)
```The longest response received length represents the correct password and username```

# 2. Brute Force -> Medium Security Level
```The only differnce is the timing from else condition```
![The only difference](images/5.png)
 
```bash
Foxy Proxy ON, send to intruder 
Same workflow, just modify the user payload and password payload from burp
```
**The fastest response is the correct combination of user and pass**
![alt text](images/6.png)
# 3. Brute Force -> High Security Level
![alt text](images/7.png)
```bash
Generate Anti CSRF Token
After some research i found that the Cross-site request forgery (also known as CSRF) is a web security vulnerability that allows an attacker to induce users to perform actions that they do not intend to perform. It allows an attacker to partly circumvent the same origin policy, which is designed to prevent different websites from interfering with each other.
```

**Inspect element to show the user token**
![alt text](images/8.png)

``` bash
Pitchfork attack with the admin username
Select the payloads -> password and user_token
At the first payload select the password.txt file and for user_token select Payload type - Recursive grep
```
![alt text](images/9.png)
![alt text](images/10.png)
![alt text](images/11.png)

We are in 
![alt text](images/12.png)