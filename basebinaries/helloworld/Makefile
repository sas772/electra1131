TARGET  = helloworld
OUTDIR ?= bin

CC      = xcrun -sdk iphoneos cc -arch arm64
LDID    = ldid
CFLAGS  = -Wall

.PHONY: all clean

all: $(OUTDIR)/$(TARGET)

DEBUG ?= 0
ifeq ($(DEBUG), 1)
else
    CFLAGS += -O2
endif

$(OUTDIR):
	mkdir -p $(OUTDIR)

$(OUTDIR)/$(TARGET): *.c | $(OUTDIR)
	$(CC) -o $@ $^ $(CFLAGS)
	$(LDID) -SEnt.plist $@

clean:
	rm -f $(OUTDIR)/$(TARGET)
