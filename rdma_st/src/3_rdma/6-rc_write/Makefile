CC = gcc
OFED_PATH = /usr
DEFAULT_CFLAGS = -I${OFED_PATH}/include
DEFAULT_LDFLAGS = -L${OFED_PATH}/lib64 -L${OFED_PATH}/lib

CFLAGS += $(DEFAULT_CFLAGS) -g -O2 -Wall -Werror
LDFLAGS += $(DEFAULT_LDFLAGS) -libverbs
OBJECTS = hello_world_rc_write.o sock.o
TARGETS = hello_world_rc_write

all: $(TARGETS)

hello_world_rc_write: hello_world_rc_write.o sock.o
	$(CC) $^ -o $@ $(LDFLAGS)

hello_world_rc_write.o: hello_world_rc_write.c sock.h
	$(CC) -c $(CFLAGS) $<

sock.o: sock.c sock.h
	$(CC) -c $(CFLAGS) $<

clean:
	rm -f $(OBJECTS) $(TARGETS)

