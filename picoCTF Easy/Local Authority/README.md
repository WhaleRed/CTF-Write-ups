# Description
Can you get the flag?
Go to this website and see what you can discover.

# Hint
1. How is the password checked on this website?

# Capture start
Upon launching the instance you will be asked to go to the website.
Once you are in the website you can inspect the element of the website.

![image](https://github.com/user-attachments/assets/482c030d-5c94-449d-8663-edd8044b8a1c)

We might be using a different browser but the method of capture will be the same.
I moved to the sources tabs. In my case this is where i can see the source code of the website.

![image](https://github.com/user-attachments/assets/ac41079d-dd5d-4964-84ec-a213eddf3303)



If we try to log in with random username and password we get:

![image](https://github.com/user-attachments/assets/fb51763f-6dd1-4605-a01b-e701f54bef8b)

One of the source codes tells us what values of username and password returns true.

![image](https://github.com/user-attachments/assets/8b2bf51c-467f-409a-9cff-fb5b6193f16e)

Now we just enter these values in their respective text field and we should get the flag.

![Screenshot 2024-10-23 182430](https://github.com/user-attachments/assets/d01e346c-6480-480c-8c47-c0f7930b70fb)

Date written: 23 October 2024
