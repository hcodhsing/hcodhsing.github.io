Linux Swap File
Alternatively, you can create a Linux Swap File after the installation. The modern Linux Kernel allows Swapping to a swap file instead of a swap partition. A swap file has an advantage over a swap partition that you can change the size of your swap any time easily by changing a swap file size.

If you want to create a swap file, run this command first:
```
sudo fallocate -l 8G /swapfile
```
Note: this command is to create a 1Gb swap file. Replace 1G with the value you want.

Next, you have to set the correct permissions.
```
sudo chmod 600 /swapfile
```
Then, format the file to swap.

```
sudo mkswap /swapfile
```
Finally, enable the swap.
```
sudo swapon /swapfile
```
Edit the file and add the following./etc/fstab
```
/swapfile none swap sw 0 0
```
