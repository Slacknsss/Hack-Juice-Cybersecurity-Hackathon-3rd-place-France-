##### **Methodology:**
To post some feedback in another user's name my first id was to tchek the main.js and ctrl-f as always to find some user's function to see how its done , then i find nothing and try to intercepet the POST request when submiting a feedback .


##### **Vulnerability:**
i catch it 
![image](https://cdn.discordapp.com/attachments/1447961589973254244/1447973010739822734/Capture_decran_2025-12-09_a_16.26.46.png?ex=69399173&is=69383ff3&hm=581febee87002c66b922650523b2ffeee4404aef9c930778de1501f6d1cc91e9&)
then i just try to change the user id by 2, (was 1)

[image](https://cdn.discordapp.com/attachments/1447961589973254244/1447977016581427293/Capture_decran_2025-12-09_a_16.42.05.png?ex=6939952e&is=693843ae&hm=ab9e39d301e074e7ba79878e21d75692de4ece520f71426375bb707978a600ec&)

and bingo , thats creat a new comment on from an other user .
##### **Risks:**





##### **Actions:**
Burp reapter changing user id 