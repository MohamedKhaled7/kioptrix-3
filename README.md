 
  
this Kioptrix VM Image is an easy challenge. The object of the game is to acquire root access via any means possible (except actually hacking the VM server or player). The purpose of these games are to learn the basic tools and techniques in vulnerability assessment and exploitation. There are more ways than one to complete the challenges.
 
##  Gain root access on this machine:  ##

####  Start the Kioptrix VM on VirtualBox or VMware ####
 ![Kioptrix_Level_1-1](https://user-images.githubusercontent.com/58820314/112413283-9997c200-8d28-11eb-877e-4c53a79bb04e.png)
 
 • Know your IP and interface using this command : **sudo ifconfig**
 ![1](https://user-images.githubusercontent.com/58820314/112559678-264e8880-8dda-11eb-8fec-2aaa8ea44a23.png)

 • Discover the Network to obtain the IP of this machine with : **sudo netdiscover -i eth0** 
 ![1](https://user-images.githubusercontent.com/58820314/112777373-60ba5e80-9042-11eb-8663-e6ba1fb38b75.png)
 
 ![2](https://user-images.githubusercontent.com/58820314/112777378-644de580-9042-11eb-8c80-22122ffee78c.png)



• Next step is to scan for vulnerabilities using **Nmap** by this command: **nmap -A -T4 192.168.3.132**
 ![3](https://user-images.githubusercontent.com/58820314/112777404-7760b580-9042-11eb-82cf-e3bf20d686f0.png)

### open the web page and this is appears ### 
![4](https://user-images.githubusercontent.com/58820314/112777527-c73f7c80-9042-11eb-8530-b86e6c6565b9.png)

 ### we will open the web page of this machine and try some **SQL and command injection** and **command injection** as well and we figured out that command injection worked    ###
 ![5](https://user-images.githubusercontent.com/58820314/112777551-d1617b00-9042-11eb-9a68-5b25af77d9aa.png)
![6](https://user-images.githubusercontent.com/58820314/112777557-d292a800-9042-11eb-8ddb-d5f02927b525.png)

  ###  set up our proxy on firefox and burpsuite to intercept traffics and save them in a file    ###
 ![7](https://user-images.githubusercontent.com/58820314/112777656-0968be00-9043-11eb-84df-c90ff27f3d14.png)
 ![8](https://user-images.githubusercontent.com/58820314/112777658-0a015480-9043-11eb-98d4-c8a9416be408.png)


### Here we used MYSQL to scan content of this page and extracte Users and tabels  ###
 ![10](https://user-images.githubusercontent.com/58820314/112777763-4df45980-9043-11eb-9c66-d39b8a61b145.png)

### we found a table contain accounts , let's try to scan it using MYSQL  ###
![11](https://user-images.githubusercontent.com/58820314/112777838-74b29000-9043-11eb-9a64-2d8d3b8e0fb6.png)
 ### The Results are   ###
 ![12](https://user-images.githubusercontent.com/58820314/112777884-8b58e700-9043-11eb-854e-9fc35ff5d41a.png)
### now let's try to connect using ssh on port 22 using user shown in the table  ###
![14](https://user-images.githubusercontent.com/58820314/112777951-b04d5a00-9043-11eb-8fa9-75a6a19b320b.png)
### Follow the commands and this will show with you ###
![15](https://user-images.githubusercontent.com/58820314/112777986-cd822880-9043-11eb-9540-21a84377f27d.png)
### Press **F3** to open this pop up window and search for */etc/sudores* file to make one user as root and delete any characters before /**bin** as showm in the photo  ###
 ![16](https://user-images.githubusercontent.com/58820314/112778077-03bfa800-9044-11eb-878c-602d5e3caf3b.png)
### now let's try to access as root ### 
![17](https://user-images.githubusercontent.com/58820314/112778211-46818000-9044-11eb-8a83-88570db59af4.png)

 
