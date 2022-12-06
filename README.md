# cmpe283-assignment2
**Pawan kalyan Jonnalagadda**
---
I have completed this assigmnet using GCP Instance and this instance is enabled for nested virtualization.

**Question-1**
I have completed this assigment alone.
---

**Quesstion-2**
First we need to setup the environment

Step1: CLone the linux repo into the vm 
using : git clone https://github.com/pawankalyanj/linux.git
I have forked the linux repo into my account and cloned it.

Step2: Install all the build essentials to avoid any errors
Command: sudo apt-get install git fakeroot build-essential ncurses-dev xz-utils libssl-dev bc flex libelf-dev bison

Step3: Since we already have a config file from the assigment 1 we can use that here.

Step4: Next run make -j8 && make modules && make install and moudles install

Step5: reboot the vm to apply the changes of new kernel.
Command: sudo reboot

Step6: To check the current version run the following command.
Command: uname -a

Step7: Modify the kernel by making changes to vmx.c by creating the two global varibles I have uploaded the modified code in the repo main branch.
also create a new leaf cpuid.c file. to read the no of exits and move high 32 cpu cylces and low 32 bit cycles.

Step7: Use the below commands to load the new kernel

    sudo rmmod kvm_intel
    
    sudo rmmod kvm
    
    sudo modprode kvm
    
    sudo modprobe kvm_intel
    
    
Step8: Download the ubuntu cloud server image using Command: wget https://cloud-images.ubuntu.com/bionic/current/bionic-server-cloudimg-amd64.img

Step9: We have to set the password to boot the ubunut image create configuration file and pass the file as the user data image to login.

Step10: Install "CPUID" in the nested vm

Step 11: Now run the cpuid. file using command: gcc cpuid.cafter that we can see the following results

![Screenshot 2022-12-05 at 10 44 15 PM](https://user-images.githubusercontent.com/98665897/205847200-39e8a85d-6a48-4707-bac5-0345d109448d.png)
![Screenshot 2022-12-05 at 10 46 40 PM](https://user-images.githubusercontent.com/98665897/205847245-7fe45cde-06f7-4030-b532-448ab972c723.png)



