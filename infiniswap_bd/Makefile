ifneq ($(KERNELRELEASE),)
    # kbuild part of makefile
obj-m  := infiniswap.o
infiniswap-y := is_configfs.o is_mq.o is_main.o
ccflags-y=-I/usr/src/mlnx-ofed-kernel-3.2/include/ -I./init

else
    KDIR ?= /lib/modules/`uname -r`/build

PWD := $(shell pwd)

make:
	rm *.o *.ko *.mod.c;$(MAKE) -C $(KDIR) SUBDIRS=$(PWD) modules

clean:
	$(MAKE) -C $(KDIR) SUBDIRS=$(PWD) clean


endif
