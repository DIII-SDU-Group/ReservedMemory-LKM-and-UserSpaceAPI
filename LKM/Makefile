obj-m += reservedmemLKM.o

all:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

install:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules && sudo insmod reservedmemLKM.ko && sudo chmod 666 /dev/reservedmemLKM

reload:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules && sudo rmmod reservedmemLKM && sudo insmod reservedmemLKM.ko && sudo chmod 666 /dev/reservedmemLKM

uninstall:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean && sudo rmmod reservedmemLKM

clean:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean