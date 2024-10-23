# Description
Are overflows just a stack concern?

# Hint
1. What part of the heap do you have control over and how far is it from the safe_var?

# Capture Start
Upon launching an instance you will be given a ```netcat``` or ```nc```. You can just copy and paste it to your terminal.

</br>After pasting this should come out:

![Screenshot 2024-10-21 232848](https://github.com/user-attachments/assets/00bc792f-8f09-4904-ae87-ec218cfa7d25)

But before we play around with the ```netcat``` we should download the source code first.

```
wget https://artifacts.picoctf.net/c_tethys/29/chall.c
```

After downloading we can now view the source code with the ```cat``` command. Now if you are new to programming and is overwhelmed by the source code don't worry it is not as hard as you think it is.</br>
First what we should do is to look at the main function. Every c program have a main function. Now looking at the main function there is a switch case.

![Screenshot 2024-10-21 233716](https://github.com/user-attachments/assets/5187f81f-edbc-4db4-b697-218f31c3f08b)

If you think about it these switch cases are the choices in the netcat. One of the choices prints the flag and that choice is 4.
</br>Case 4 checks the win condition and in doing so case 4 calls a function called check_win(). Now we have to find the function.

</br>The function:

![Screenshot 2024-10-21 233544](https://github.com/user-attachments/assets/2548d194-6ae7-41c6-ab4e-d0dad5b37b39)

As you can see in the function there is an if statement. If the statement is satisfied the flag will be printed.
To satisfy the statement ```strcmp() != 0 ```, we must ensure that the ```strcmp()``` returns a value not equal to 0. To do that we must modify the value of safe_var and that value must not be equal to "bico".


Let's return to the netcat.
</br>
If we try to print the safe_var it prints out "bico".

![Screenshot 2024-10-23 150031](https://github.com/user-attachments/assets/b4243a77-a588-4217-bbeb-ca7e3488f0b1)

We have to modify this. If we look back at the heap state. You can see two different addresses and data. The first row is the adress of the input of write to buffer and the second row is the adress of the safe_var.

The only part of the heap we have control over is write to buffer and as the hint pointed out how far is it from the safe_var.
</br> This is where we whip out our calculator.

![Screenshot 2024-10-21 232632](https://github.com/user-attachments/assets/4769d26d-c2c8-4001-898a-88b660d76634)

As you can see at the ```DEC``` the write to buffer is 32 characters away from the safe_var.

If we write to buffer with 32 characters and something else it should cause an overflow.

![image](https://github.com/user-attachments/assets/f65bf34e-fdf7-4ac7-9ad7-19f07323111a)

If we print the heap it should now look like this:

![image](https://github.com/user-attachments/assets/5f0cde2f-c476-4a6f-8f72-5ea7f2807683)

The "bico" turned into "blaze" which means we change the value of safe_var into blaze.
</br>It should now print the flag.

![Screenshot 2024-10-23 151752](https://github.com/user-attachments/assets/aac07b17-b540-42ff-98fe-4a60ffe8ec34)

Date written: 23 October 2024
