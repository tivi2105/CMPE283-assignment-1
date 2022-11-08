# CMPE283-assignment-1
**In this project we will see how to discover VMX features present in our processor by writing a Linux kernel module that queries these features.**

## **Changes required in '.c' file**
* Install git and fork current repository.
* Define primary, secondary, pin-based, exit and entry controls in cmpe283-1.c as shown below:
  * #define IA32_VMX_PINBASED_CTLS		0x481
  * #define IA32_VMX_PROCBASED_CTLS 	0x482
  * #define IA32_VMX_PROCBASED_CTLS2	0x48B
  * #define IA32_VMX_EXIT_CTLS		    0x483
  * #define IA32_VMX_ENTRY_CTLS		  0x484
* Declare capability information for all controls.
* Program read and print functions for all the controls.

## **VM in Google Cloud Platform**
* Create an account in Google cloud platform and add billing information.
* Create a VM instance by selecting Series : N2; Machine chip : standard; Operating system : Ubuntu; size : 100GB and allow fire wall.
* Click on the button 'Equivalent command line' and copy the commands to create VM instance using CLI.
* Run the command in CLI by adding **--enable nested virtualization** argument along with the **--zone=us-central-1a**.
* Start(if the VM didn't start automatically) and open the VMinstance.
* Clone the forked git repository in to the VM instance.
* Install gcc, make and headers using below commands:
  * sudo apt install gcc
  * sudo apt install make
  * sudo apt-get linux-headers-$(uname -r)
* cd into the cloned repository and run make file using **make** command.
* Now, if you perform an **ls** operation you will find a cmpe283-1.ko file which is the a kernel object file.
* Run **sudo insmod ./cmpe283-1.ko** command to insert the kernel module.
* You won't see anything happening in the CLI, you should run **dmesg** command to see the output.
* The output will look like below images:

![alt text](https://github.com/tivi2105/CMPE283-assignment-1/blob/main/output_image_1.png)
![alt text](https://github.com/tivi2105/CMPE283-assignment-1/blob/main/output_image_2.png)

  
