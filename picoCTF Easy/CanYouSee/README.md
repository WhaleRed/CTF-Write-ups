# Descriptiom
How about some hide and seek?

# Hints
1. How can you view the information about the picture?
2. If something isn't in the expected form, maybe it deserves attention?

# Capture start
First we download the file.
```
wget https://artifacts.picoctf.net/c_titan/4/unknown.zip
```

Then we unzip.
```
unzip unknown.zip
```

After unzipping we get a ```jpg``` file.
Let's try viewing it with ```feh```.

```
feh ukn_reality.jpg
```

We are not getting any clues from viewing the image. So we to view the information of the image.

# Exiftool
Exiftool is used for  reading and writing meta information in a variety of file types.

If you want to know more about exiftool you can copy and paste this command to your terminal.
```
man exiftool
```
#
Now that we have a way to view the image's information, we just have to run it with the command.
```
exiftool ukn_reality.jpg
```

It should ouput this:

![image](https://github.com/user-attachments/assets/dff003ac-ba07-4424-96ad-be3ae0e03fe2)

One of the information does not look right and looks like it was encrypted using base64.

So we can try decoding it. Using this command it should decode the string.
```
echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg" | base64 -d
```
What does the command do?

```echo``` outputs the string inside the ```""```.</br>
```|``` passes the output of the previous command to the next command.</br>
```base64 -d``` decodes the passed base64 string.

After you decode the string it prints out the flag.

![Screenshot 2024-10-23 175618](https://github.com/user-attachments/assets/cc6e54e5-ee63-471d-9afe-5297cd2f4ac9)


Date written: 23 October 2024
