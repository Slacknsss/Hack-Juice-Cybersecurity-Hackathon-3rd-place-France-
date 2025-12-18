##### **Methodology:**
To put an additional product into another user's shopping basket, i use Burp again to intercept the request (`POST /api/basketitems`) when adding a product in my basket.
Then i took a look at the JSON after sending it to Repeater.

![image](./assets/basket1.png)

---

##### **Vulnerability:**
**Type:** Broken access control / IDOR (basket manipulation)  
**Component:** `POST /api/basketitems` (JSON fields like `BasketId`)  
**Severity:** High  

I try to change the JSON line by line and test. It finally work when i just add the `"BasketId"` line twice at the end (yeah weird but it works 😅):

![image](./assets/basket2.png)

Then it works!$

![image](./assets/basket3.png)
![image](./assets/basket4.png)
![image](./assets/basket5.png)

---

##### **Risks:**
You can easily add products into other people basket, so you can mess with their orders / price / checkout. Its annoying and can be used to troll or worse if it impact payment.

---

##### **Actions:**
- Intercept `POST /api/basketitems` in Burp
- Send to Repeater
- Manually change the JSON (focus on `BasketId`) and resend
