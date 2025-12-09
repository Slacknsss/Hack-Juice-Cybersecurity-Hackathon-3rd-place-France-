##### **Methodology:**
I first tcheck what is a CSRF attak, then  i discover that its just a basic fishing methode when the hacker 
use established session tokens from the user whitout any verification by making 
the user click on somethings, like a url or a basic button that contain an hidden POST request.
So i locked up on the internet some example , i tried and it doesnt work .
<!-- <h1>You Are a Winner!</h1>
  <form action="http://example.com/api/account" method="post">
    <input type="hidden" name="Transaction" value="withdraw" />
    <input type="hidden" name="Amount" value="1000000" />
  <input type="submit" value="Click Me"/>
</form> -->

Then We tried with burp, sending  a typical request by changing the name of th user in the settigns.



##### **Vulnerability:**
finding the Post request 

![image](https://cdn.discordapp.com/attachments/1447961589973254244/1447963253786411008/Capture_decran_2025-12-09_a_15.45.27.png?ex=6939885d&is=693836dd&hm=fdcd23d5aa4a055d1508a145f7fa73378a5402233b0fbf89f0c7748d3790613e&)

Then send it to  the reapeter and after changing a lot of things whithout any Flag captured , i decide to look up on internet and find a source talking about the flaws and find a way to basicaly change the origne of the websit ; that was "https://ctf.juice.cyber.epitest.eu"
by "http://htmledit.squarefree.com"


![imgae](https://cdn.discordapp.com/attachments/1447961589973254244/1447965456672751627/Capture_decran_2025-12-09_a_15.50.42.png?ex=69398a6a&is=693838ea&hm=c5b3943baa5331b6b0a3647b28bfe4efc1e146a1f3529a7f5a26cef92acd41d7&)
##### **Risks:**

idk

##### **Actions:**
brute force reapter by changing url origin in burp