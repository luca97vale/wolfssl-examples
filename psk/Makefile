CC=gcc
CFLAGS=-Wall -I/usr/local/include
LIBS=-lwolfssl -lm -L/usr/local/lib

# For debug (./configure --enable-debug --disable-shared)
#LIBS=/usr/local/lib/libwolfssl.a
#CFLAGS+=-g -DDEBUG


all: client-tcp client-psk client-psk-nonblocking client-psk-resume server-tcp server-psk server-psk-nonblocking server-psk-threaded

client-tcp: client-tcp.o
	$(CC) -o $@ $^ $(CFLAGS)

client-psk: client-psk.o
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

client-psk-nonblocking: client-psk-nonblocking.o
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

client-psk-resume: client-psk-resume.o
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

server-tcp: server-tcp.o
	$(CC) -o $@ $^ $(CFLAGS)

server-psk: server-psk.o
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

server-psk-nonblocking: server-psk-nonblocking.o
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

server-psk-threaded: server-psk-threaded.o
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS) -lpthread

.PHONY: clean all

clean:
	rm -f *.o client-tcp client-psk client-psk-nonblocking client-psk-resume server-tcp server-psk server-psk-nonblocking server-psk-threaded
