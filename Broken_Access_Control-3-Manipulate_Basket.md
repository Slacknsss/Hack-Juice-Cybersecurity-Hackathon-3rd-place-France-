##### **Methodology:**
To put an additional product into another user's
shopping basket is use burb again to intercetp the request (POST /api/basketitems, when adding a product in the basket);
Then i took a look in the JSON fil after send it to the repeater:
![image](./assets/basket1.png)
##### **Vulnerability:**
i try to change a ligne per ligne the content of the Json 
and it was finnaly working when i logicaly add  the "BasketId" line twice at the end:
![image](./assets/basket2.png)
thats working !$
![image](./assets/basket3.png)
![image](./assets/basket4.png)
![image](./assets/basket5.png)
##### **Risks:**
you  can easely add products on other basket ,that annoying
##### **Actions:**
brup reapter , manualy change the json part 
