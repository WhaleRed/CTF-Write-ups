#CTF Description
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?

#Hints
1. QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.
2. Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11
3. If you don't have access to a phone, you can also use zbar-tools to convert an image to text

#Capture Start

This code will download the challenge file
```
wget https://artifacts.picoctf.net/c_atlas/14/challenge.zip
```

Since its a zip file we unzip it

```
unzip challenge.zip
```
After that we use the command ```ls``` to see the list of all files in the directory.
You should see something like this
Insert Image here

Now we just have to move to the deepest part of the directory by using the ```cd``` command.
The process of moving to the deepest part of the directory should look like this.
Insert Image here

After we arrive to the deepest part of the directory we can see a png file.
Let's find a way to take a look at the png file.

#```feh```
The ```feh``` command  is a light-weight, configurable and versatile image viewer.
if you want to read more about the feh command you can type ```man feh``` in your terminal.

Now that we have a way to view the png file. We can view it by typing this in the terminal.
```feh flag.png```
This should print out a QR code which you can scan with a scanner.
After you scan the QR it should show the flag.
