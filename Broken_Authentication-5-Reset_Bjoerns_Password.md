**Reset the password of Bjoern's internal account via the Forgot Password mechanism with the original answer to his security question. (Difficulty Level: 5)**
**##### **Methodology:****
Vamos do some osint again , i took his email (bjoern@juice-sh.op) and do forget passwrd , then the quesiton is ;"Your ZIP/postal code when you were a teenager?" 
i then stalk the facebook of Bjoern and find this
![image](./assets/bj1.png)
look up on the internet 
![image](./assets/bj2.png)

25436 is not working for the code
![image](./assets/bj3.png) 
so i knew that was thas bc i found  nothing else.
i start to encode the code in base64, not working?
I realise that was 35 years ago so maybe that syntax for Code postal change !
Indeed that change so i find a convertisor 
![image](./assets/bj4.png)
try West-2082

![image](./assets/bj5.png)
it works lol



**##### **Vulnerability:****

**##### **Risks:****

**##### **Actions:****
