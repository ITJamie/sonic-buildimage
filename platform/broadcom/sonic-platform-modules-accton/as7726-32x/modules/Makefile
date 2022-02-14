ifneq ($(KERNELRELEASE),)
obj-m:= accton_as7726_32x_cpld.o accton_as7726_32x_fan.o  \
	    accton_as7726_32x_leds.o accton_as7726_32x_psu.o ym2651y.o \
	    pddf_custom_psu.o

CFLAGS_pddf_custom_psu.o := -I$(M)/../../../../pddf/i2c/modules/include
KBUILD_EXTRA_SYMBOLS := $(M)/../../../../pddf/i2c/Module.symvers.PDDF
    
else
PWD:=$(shell pwd)
default:
	$(MAKE) -C $(KERNEL_SRC)  M=$(PWD) modules
clean:
	rm -rf *.o *.mod.o *.mod.o *.ko .*cmd .tmp_versions Module.markers Module.symvers modules.order
endif
