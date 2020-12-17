# **RedHat Kernel Upgrading and Downgrading**
*OS: Redhat Enterprise Linux 8.2
Linux Updated Kernel 4.18.0- 193.19.1.el8_2.x86_64 (This kernel version is our requirment)
Default Linux Kernel 4.18.0- 193.28.1.el8_2.x86_64 (This is default kernel version)
Steps:
1.	Linux Kernel Upgrading/Downgrading method:

Following link for downloading the required kernel version but you can follow as per your requirements: 
Link: https://rpmfind.net/linux/RPM/centos/8.2.2004/baseos/x86_64/Packages/kernel-4.18.0-193.19.1.el8_2.x86_64.html 

2. Direct Installation from web using dnf

Run this command on terminal
# dnf install <link>
e.g https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm

Note: Update the above web link of downloading file source after dnf install. 

3.	Easy steps to change default kernel version RHEL/CentOS 
4. Check the isntalled kernels in the systems using this command 
# rpm -qa | grep kernel | sort
you cant find the kernel in the list with versions which you installed recently. check your installed kernel version in the lsit.
5. currently active kernel version
# uname -r
6. We can check all the available boot items using grubby
# grubby --info="/boot/vmlinuz-4.18.0-193.14.3.el8_2.x86_64" 
7. Now active the kernel version which we need using this command
# grubby --set-default "/boot/vmlinuz-4.18.0-193.1.2.el8_2.x86_64"
8. Now Reboot the system and check the kernel is updated 
# reboot
# uname -r
