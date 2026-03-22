# HTTP server on single board computer

``Entire proces was made on orange pi 4 pro but it'll work just well on any of the pc's that have armbian os installed. Server will be set up by using additional laptop with windows or linux (steps are the same)  with ssh installed.``

## SSH
The thing we'll controll our board with. We're going to do this in our windows powershell / linux terminal. We need a few informations about our board to do it tho:
- Our board ip adress
- our board username
- our board username password

Now we can connect with our board by typing from this template:
```
ssh <board username>@<board ip adress>
```

When the terminal of our board pops up, then you know you did well

## Changing your board ip to static
That's the thing I can't exactly help you with, cuz it's related to your router which can be diffrent for each one of you. Search for it on your router ip adress site

## Installing apache
Apache is a server that will host our website, we install it by typing:
```
sudo apt install apache2 -y
```

## Checking if the instalation went right
After installing it, we need to check if it works now, we do it by going onto our board ip by browser. We want to see that page:
<img width="397" height="460" alt="image" src="https://github.com/user-attachments/assets/1ac85fb7-ed76-458e-bd20-8d681071e101" />

When we see it, we know everything works well

## Transfering our files
Page files are located in folder `/var/www/html/`. We want to transfer our own files there. To give you all a quick try, you can use files from my portfolio: https://github.com/Sleppy-af/Portfolio

Before transfering them tho, we want to delete basic apache index file by entring the direcotry of it
```
cd /var/www/html/
```
Checking if it's there
```
ls
```
and then deleting it
```
rm index.html
```


Now we can transfer our files by:
```
scp <path to your file PC> <board username>@<board ip adress>:<path where you want to have the files on your board>
```

## Final look
Now when we go onto our board ip, we should see the website we wanted

And that's all, see ya in the next tutorials :3
