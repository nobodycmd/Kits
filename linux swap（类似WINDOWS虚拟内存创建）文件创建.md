
## link https://www.thegeekstuff.com/2010/08/how-to-add-swap-space/
 
 ### The following dd command example creates a swap file with the name “myswapfile” under /root directory with a size of 1024MB (1GB).
 * dd if=/dev/zero of=/root/myswapfile bs=1M count=1024  (1024个1M那就是1G，can change the value to what u want）
 
 ###  Change the permission of the swap file so that only root can access it.
  * chmod 600 /root/myswapfile
  
 ### Make this file as a swap file using mkswap command.
 *  mkswap /root/myswapfile
 
 ### Enable the newly created swapfile.
 * swapon /root/myswapfile
 
 ### To make this swap file available as a swap area even after the reboot, add the following line to the /etc/fstab file.
 *  cat /etc/fstab 
 * /root/myswapfile               swap                    swap    defaults        0 0
 
 ### Verify whether the newly created swap area is available for your use.
  * swapon -s
  * free -k
  
 ~~~
 If you don't want to reboot to verify whether the system takes all the swap space mentioned in the /etc/fstab, 
 you can do the following, which will disable and enable all the swap partition mentioned in the /etc/fstab
  swapoff -a
  swapon -a
  ~~~
