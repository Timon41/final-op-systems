# final-op-systems
there the command for the first task


$sudo -i #for going with root

$useradd TaGaNuYeAd #it is for our names

$passwd cisco #giving password

$login #login to this user

$whoami #to clarify

$logout #go out from this user

So there we commands for the 2 task


$ping #for the checking connections

3 task


There we need commands

Create a new directory for module:

$mkdir mymodule 

$cd mymodule #for the going to this file

$ nano mymodule.c #for the developing and adding codes inside

$ nano Makefile  #also for editing

#include <linux/init.h>
#include <linux/module.h>

MODULE_LICENSE("GPL");

static int __init mymodule_init(void) {
    printk(KERN_INFO "Hello, User!\n");
    return 0;
}

static void __exit mymodule_exit(void) {
    printk(KERN_INFO "Goodbye, User! You do not want stay?\n");
}

module_init(mymodule_init);
module_exit(mymodule_exit); #this is for the inside in mymodule


This inside Makefile

obj-m += mymodule.o

all:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

clean:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean
	
Write command $ make to build module

$ sudo insmod mymodule.ko

$ sudo insmod mymodule.ko #this will display our commands that was inside mymodule
