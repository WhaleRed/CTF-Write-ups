# CTF Description
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?

# Hints
1. QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.
2. Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11
3. If you don't have access to a phone, you can also use zbar-tools to convert an image to text

# Capture Start

This command will download the challenge file
```
wget https://artifacts.picoctf.net/c_atlas/14/challenge.zip
```

Since its a zip file we unzip it

```
unzip challenge.zip
```
After that we use the command ```ls``` to see the list of all files in the directory.
You should see something like this

![Screenshot 2024-10-20 144612](https://github.com/user-attachments/assets/7e51e6bf-db9b-421d-9b59-62f95e6a8f27)

Now we just have to move to the deepest part of the directory by using the ```cd``` command.
The process of moving to the deepest part of the directory should look like this.

![Screenshot 2024-10-20 145022](https://github.com/user-attachments/assets/f828d82c-07fa-4085-b270-588980052199)


After we arrive to the deepest part of the directory we can see a png file.
Let's find a way to take a look at the png file.

# ```feh```
The ```feh``` is a light-weight, configurable and versatile image viewer.
if you want to read more about the feh command you can type ```man feh``` in your terminal.

Now that we have a way to view the png file. We can view it by typing this in the terminal.
```
feh flag.png
```
This should print out a QR code which you can scan with a scanner.
After you scan the QR it should show the flag.


Date written: 20 October 2024

