##### **Methodology:**
As i did befor i try to catch the request when i post a feedback on an example.

![image](./assets/screnne6.png)

Then i find the request in Burp:

![image](./assets/screnne7.png)

I send it to Repeater to try to change the message in the JSON and also the user mail.

![image](./assets/s7.png)

TO

![image](./assets/s8.png)

Then we can see it add a comment from the second email (`caca@gmail.com`).

![image](./assets/s9.png)

---

##### **Vulnerability:**
**Type:** Client-side trust / spoofable author field (JSON tampering)  
**Component:** Feedback API (JSON fields like `message` / `author` / `email`)  
**Severity:** High  

Basically the backend trust what i send in the JSON, so i can change the author/sender.

---

##### **Risks:**
- You can impersonate any email/user in comments (fake feedbacks)
- Can be used for scam / trolling / reputation damage
- If same logic exist somewhere else, it can lead to bigger account/data problems

---

##### **Actions:**
- Intercept feedback POST request
- Send to Burp Repeater
- Change JSON `message` + `author/email` and resend
