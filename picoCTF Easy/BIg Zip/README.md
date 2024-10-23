# Description
Unzip this archive and find the flag.

# Hint
Can grep be instructed to look at every file in a directory and its subdirectories?

# Capture Start
We first download the zip file.
```
wget https://artifacts.picoctf.net/c/504/big-zip-files.zip
```

Then we unpack the zip file.

```
unzip big-zip-files.zip
```

The hint ask us if the grep can be instructed to look at every file in a directory and its subdirectories. 
</br>To know if we can do that we can run the command ```grep --help```.
This should printout many ways of using the ```grep``` command.
One of the printed ways is:
```
  -r, --recursive           like --directories=recurse
```

Now that we know that ```grep``` can be used recursively we can just run grep with the additional instruction.
```
 grep -r "picoCTF"
```

It should then search for the pattern "picoCTF" in the directory and each subdirectories.

![Screenshot 2024-10-23 154847](https://github.com/user-attachments/assets/362cc4d4-5a0c-4596-a43c-4cc9aa921ff2)

Date written: 23 October 2024
