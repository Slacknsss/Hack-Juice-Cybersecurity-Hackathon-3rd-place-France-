##### **Methodology:**
When i saw "access" i directly think about changing the URL 
So i look up on internet how to brute force URL paths.

We already know the `/ftp` path because of the confidential challenge where we explore "About us" and find it inside a link:

![image](./assets/Access1.png)

Then we explore the ftp page:

![image](./assets/Access2.png)

After that i learn how to brute force hidden paths with Burp Intruder.
I start with a basic GET request, send it to Intruder, and use a payload position for the path (like `GET /$path$ HTTP/2`).
Then i put a list of common paths i found on google:

![image](./assets/Access3.png)

I got this:

![image](./assets/Access6.png)

So i saw `/ftp` got a different length, so i assume its a real endpoint.
Most of the other paths got the same size, so i think it can be a catch-all (Angular style), so i keep testing.

I try with `support` because i see this word a lot in error messages.
So i test stuff like `/support/<word>` with some keywords i found from other web debunkers lists:

![image](./assets/Access4.png)
![image](./assets/Access5.png)

It works with `logs`, so i try the final path:

`https://ctf.juice.cyber.epitest.eu/support/logs`

And i got this:

![image](./assets/Access7.png)

Green flag 

---

##### **Vulnerability:**
**Type:** Forced browsing / hidden endpoint discovery  
**Component:** Web routing (hidden paths like `/support/logs`)  
**Severity:** Medium  

---

##### **Risks:**
- Sensitive pages like logs/support panels can be accessible just by guessing the URL
- Info leak (paths, internal data, errors, maybe tokens/logs)
- Helps attackers map the app faster

---

##### **Actions:**
- Use known endpoint (`/ftp`) as starting point
- Burp Intruder brute force common paths
- Compare response length/status to detect real endpoints
- Find `/support/logs` and access it
