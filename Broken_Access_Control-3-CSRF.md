##### **Methodology:**
I first tcheck what is a CSRF attak, then  i discover that its just a basic fishing methode when the hacker 
use established session tokens from the user whitout any verification by making 
the user click on somethings, like a url or a basic button that contain an hidden POST request.
So i locked up on the internet some example , i tried and it doesnt work .

![image](./assets/screnne5.png)

Then We tried with burp, sending  a typical request by changing the name of th user in the settigns.



##### **Vulnerability:**
finding the Post request 

![image](./assets/screnne2.png)

Then send it to  the reapeter and after changing a lot of things whithout any Flag captured , i decide to look up on internet and find a source talking about the flaws and find a way to basicaly change the origne of the websit ; that was "https://ctf.juice.cyber.epitest.eu"
by "http://htmledit.squarefree.com"


![imgae](./assets/screnne1.png)
##### **Risks:**

idk

##### **Actions:**
brute force reapter by changing url origin in burp