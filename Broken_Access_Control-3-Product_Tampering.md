##### **Methodology:**
For this challenge i just try to change parameters in Burp, and explore all the ways to edit a request.
I learn from a website that you can replace `GET` by `OPTIONS` to see which methods are allowed.
So i do that and i saw that `PUT` is available 😅

Then i want to parcourir through the API, so i try this:

`PUT /api/products/9/ HTTP/2`

I send it and i got a JSON response, so i can see all the fields:

![image](./assets/Tampering1.png)

After that i just update the JSON (with some URL-slack lol):

![image](./assets/Tampering2.png)

And i got the proof that it changed:

![image](./assets/Tampering3.png)

---

##### **Vulnerability:**
**Type:** API tampering / missing authorization on PUT  
**Component:** `PUT /api/products/{id}/` (product fields editable)  
**Severity:** High  

Basically i can edit product data directly by sending a PUT request, without being admin.

---

##### **Risks:**
- Anyone can change products infos (name, description, links, etc.)
- Bad people can put phishing links or malware links in the product fields
- Can destroy the shop integrity and trust

---

##### **Actions:**
- Test `OPTIONS` to find allowed methods
- Use Burp Repeater to send a `PUT` on `/api/products/{id}/`
- Modify JSON fields and resend to confirm change
