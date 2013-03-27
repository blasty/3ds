OBJS = fs.o crypto.o wearlevel.o helper.o fuse_glue.o main.o
LIBS = -lssl -lcrypto -lfuse
CFLAGS = -Wall -ggdb -D_FILE_OFFSET_BITS=64 -DFUSE_USE_VERSION=22 
UNAME := $(shell uname)

ifeq ($(UNAME), Darwin)
CFLAGS = -Wall -ggdb -D_FILE_OFFSET_BITS=64 -DFUSE_USE_VERSION=25 -D__FreeBSD__=10
endif
ifeq ($(UNAME), Linux)
CFLAGS= -Wall -ggdb -D_FILE_OFFSET_BITS=64 -DFUSE_USE_VERSION=22
endif

OUTPUT = 3dsfuse
main: $(OBJS)
	gcc -o $(OUTPUT) $(OBJS) $(LIBS)
clean:
	rm -f $(OUTPUT) $(OBJS)
