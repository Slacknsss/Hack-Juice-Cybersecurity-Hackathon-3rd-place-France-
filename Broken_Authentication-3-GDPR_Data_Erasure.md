##### Methodology:
First thing i do is to find the Chris account, so i use again SQL injection to access the user database and see if the user is really “erased” or just hidden.

![image](./assets/GDPR2.png)

Then i basically try to login with a super short password (like 1 character) just to see how the request behave, and the challenge validate itself 😅

![image](./assets/GDPR.png)

---

##### Vulnerability:
**Type:** Broken deletion / GDPR bypass (erased account still usable)  
**Component:** User database + login flow (deleted users still authenticable)  
**Severity:** High  

---

##### Risks:
- “Deleted” accounts can still be accessed, so GDPR/erasure is fake
- Old accounts can be taken back / abused (impersonation, data access)
- Trust issue + legal risk if personal data is supposed to be removed

---

##### Actions:
- Check user existence via SQLi in user DB
- Try login on the erased account (minimal input test)
- Confirm the account is still valid even after “erase”
