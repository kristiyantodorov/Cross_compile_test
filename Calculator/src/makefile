INCLUDE_DIR=/home/devteam/OpenWRT_build/openwrt/staging_dir/target-i386_i486_uClibc-0.9.33.2/usr/include

CC=/home/devteam/OpenWRT_build/openwrt/staging_dir/toolchain-i386_i486_gcc-4.8-linaro_uClibc-0.9.33.2/bin/i486-openwrt-linux-gcc
LD=/home/devteam/OpenWRT_build/openwrt/staging_dir/toolchain-i386_i486_gcc-4.8-linaro_uClibc-0.9.33.2/bin/i486-openwrt-linux-ld

LD_LIBRARY_PATH=/home/devteam/OpenWRT_build/openwrt/staging_dir/toolchain-i386_i486_gcc-4.8-linaro_uClibc-0.9.33.2/lib/libc.so.0

LDFLAGS=-L/home/devteam/OpenWRT_build/openwrt/staging_dir/target-i386_i486_uClibc-0.9.33.2/usr/lib -lpthread -lprotobuf-c -lrt

SOURCES=calculator.c calculation.pb-c.c result.pb-c.c

OBJS=$(SOURCES:.c=.o)

all: calculator
calculator.o: calculator.c
	$(CC) -c -I $(INCLUDE_DIR) $(LDFLAGS) -o $@ $<

%.o: %.c %.h
	$(CC) -c -I $(INCLUDE_DIR) $(LDFLAGS) -o $@ $<

calculator: $(OBJS)
	$(CC) $(LDFLAGS) -o calculator $(OBJS)

clean:
	rm *.o
