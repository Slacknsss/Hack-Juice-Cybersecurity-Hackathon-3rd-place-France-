##### Methodology:
I log in on the Bender account (from the previous reset password challenge).
Then i go to the "change password" settings and i try to catch the request when i submit a new password (i put a fake current password just to generate the req).

![image](./assets/CBP1.png)

After that i look at the request and try to understand how the params are working (current / new / repeat).
I send it to Repeater and i try to change only the `new` + `repeat` values to `slurmCl4ssic`.
At first i got some `401`, but after a few tries it finally accepted the change.

![image](./assets/CBP2.png)

And proof after:

![image](./assets/CBP3.png)

---

##### Vulnerability:
**Type:** Broken password change validation (server-side check weak / bypassable)  
**Component:** Change password endpoint (params: current/new/repeat)  
**Severity:** High  

---

##### Risks:
- Anyone with access to an account session can change the password too easily
- Can lead to full account takeover if the current password is not properly verified
- If this endpoint is accessible in weird ways (like GET params), its even worse

---

##### Actions:
- Intercept change password request in Burp
- Send to Repeater
- Modify `new` + `repeat` to target password and replay until success
