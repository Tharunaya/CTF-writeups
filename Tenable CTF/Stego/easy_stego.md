# Easy Stego - 25 points
##### Message
Can you find the flag?
##### Content
![blm](blm.png)
##### Solution
The image consisted of three seperate images, each in a different colour. I decided to use the tool stegsolve for getting a better look at it. A download can be found here: https://github.com/eugenekolo/sec-tools/tree/master/stego/stegsolve/stegsolve. By executing the command ``` java -jar stegsolve.jar  ```, stegsolve is started. Now, the image can be opened and viewed in different filters. 
![blm](blm.png)
On the images, we can now see the flag:
``` flag{Bl4ck_liv3S_MATTER} ```
