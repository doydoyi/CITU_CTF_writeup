# CITU_CTF_writeup
Writeups for CTF

Steg problems solves were basically running them in Aperi'Solve. First showed the flag with Zsteg. Second one showed the flag in the Decomposer. <img width="2856" height="1824" alt="Screenshot_20250731_160334" src="https://github.com/user-attachments/assets/b4ac4a73-956f-47f3-ab2b-2d9538cee03f" />
<img width="2856" height="1824" alt="Screenshot_20250731_160622" src="https://github.com/user-attachments/assets/51588f0d-5ce2-4590-8f34-69100f8da680" />

As for the "Unsuscriptions Are Free" problem, it was a past PicoCTF2021 challenge under the binary exploitation I practiced on, it felt oddly familiar. Didn't expect it to be the same problem hehe.

<img width="300" height="300" alt="hehehe_ezpwn" src="https://github.com/user-attachments/assets/d5306036-12d9-405c-84f7-3ac5eebc3aea" />

<img width="2856" height="1824" alt="past_picoCTF_Challenge" src="https://github.com/user-attachments/assets/ef53d38a-c5e2-43b1-a08a-57ee7533a3a7" />

So I looked back on the ```Use After Free``` vulnerability python script.  
```The script```: Uses ```pwntools```, changed p.remote() with the challenges' ip and service port. A loop to get address from the leak stores it in the variable ```inp``` then converts it to a hex, ```p.sendline(b"I")``` to free the ```user```. Send "L" in order to Load or Reallocate memory, sleeps machine/challenge, Overwrote a freed memory chunk with the leaked address which will run the function to print the flag ```CITU{CWE_416_USE_AFTER_FREE}```.      
