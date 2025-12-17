
**Log in with Bjoern's Gmail account without previously changing his password, applying SQL Injection, or hacking his Google account. (Difficulty Level: 4)**
**##### **Methodology:****
i search on the main.js diff keys word like authentification/login/code/password/authlogin,
and find an interresting bloc ;
![image](./assets/LB1.png)
more specifically this line :
const i = btoa(o.email.split("").reverse().join(""));
i look up on the internet to find what it does:
 btoa() is just a base64 encoding function, and it is just encoding a reversed string consisting of the user’s email address

so i reverse the string : 
![image](./assets/LB2.png)
and decode it with the Burb decoder;
![image](./assets/LB3.png)

it works 
![image](./assets/LB4.png)

**##### **Vulnerability:****

**##### **Risks:****

**##### **Actions:****