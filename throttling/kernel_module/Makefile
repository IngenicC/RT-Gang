# This Makefile builds bwlockmod kernel module.  The generated executables are
# placed in the 'exe' directory
#
# Auhtor	: Waqar Ali (wali@ku.edu)

TOP_DIR 	:= $(shell pwd)
MOD_EXE 	:= $(TOP_DIR)/bwlockmod.ko

KVERSION 	:= $(shell uname -r)
BLDDIR 		:= /lib/modules/$(KVERSION)/build

all: setup module move
	@echo "> Build Complete. Outputs can be seen in exe directory"

setup:
	@mkdir -p exe
	@rm -f exe/*

module:
	@echo "> Building Perf-Kernel Module"
	@make -C $(BLDDIR) M=$(PWD) modules

move:
	@mv $(MOD_EXE) exe/.

clean:
	@echo "> Executing Clean Target"
	make -C $(BLDDIR) M=$(PWD) clean
	@rm -rf exe
	@echo "> Cleaning Complete"
