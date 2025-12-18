##### **Methodology:**
I started from the About us page, with the “more” link that make us discover a `/ftp` path, including files like `suspicious_error.yml` and `package.json.bak`.

![image](./assets/forgottent1.png)

But we can’t access them because the site block it with: "Error: Only .md and .pdf files are allowed!"

So i use Burp Suite to intercept the request and play with the filename in the URL:

![image](./assets/forgottent2.png)

I changed the filename by using a null-byte trick + double URL encoding (so the filter think it ends with `.md`, but the server/file part read the real filename before the null byte).

![image](./assets/forgottent3.png)

The idea: the filter checks the extension after decoding, sees something ending by `.md` so it allows it, but the backend/file open stop at the null byte and load the original file.

---

##### **Vulnerability:**
**Type:** Null byte injection / double URL-encoding bypass (extension filter bypass)  
**Component:** File access filter (allowed extensions: `.md` / `.pdf`)  
**Severity:** High  

---

##### **Risks:**
- Access to sensitive/internal files that should be blocked (`.yml`, `.bak`, configs, backups, etc.)
- Info leak (secrets, paths, tokens, debug data)
- Can lead to bigger compromise if configs/keys are exposed

---

##### **Actions:**
- Intercept request with Burp
- Use null byte poisoning + double URL encoding to bypass extension filter
- Request the blocked file through the bypassed path

![image](./assets/forgottent3.png)
