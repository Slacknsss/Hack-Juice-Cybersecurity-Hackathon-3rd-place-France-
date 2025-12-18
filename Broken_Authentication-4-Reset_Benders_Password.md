##### Methodology:
First i see the hint and i understand bender is the robot from Futurama 

![image](./assets/AB1.png)

So i start stalking where he had his first job / where he was working at the beginning:

![image](./assets/AB2.png)

Then i try different syntaxes for "suicide booth" answers but nothing was correct...
After discussing with a friend, he told me to check the suicide booth on google images.

So i do that, and i finally find the brand name written on it: Stop'n'Drop

![image](./assets/AB3.png)

Then i try `Stop'n'Drop` and it complete the challenge:

![image](./assets/AB4.png)

---

##### Vulnerability:
**Type:** OSINT / guessable security question  
**Component:** Forgot password / security question (answer found on public infos)  
**Severity:** Medium  

---

##### Risks:
If the security question answer is public/guessable, anyone can reset an account just by doing OSINT.

---

##### Actions:
- Search the hint (Futurama / Bender)
- Use google + images to find the exact brand name
- Try the final answer in the challenge
