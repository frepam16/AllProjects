CFLAGS?=-I$(shell gcj -print-file-name=include/)
CFLAGS+=-fPIC
LDFLAGS?=
LDLIBS?=`pkg-config --libs jack`
LDPATH?=
LIBRARY_PREFIX?=lib
LIBRARY_NAME?=tuxguitar-jack-jni
LIBRARY_EXTENSION?=.so

LIBRARY=$(LIBRARY_PREFIX)$(LIBRARY_NAME)$(LIBRARY_EXTENSION)
OBJECTS=org_herac_tuxguitar_jack_JackClient.o

%.o: %.c
	$(CC) $(CFLAGS) -c -o $@ $<

all:    $(LIBRARY)

$(LIBRARY):	$(OBJECTS)
	$(CC) $(LDFLAGS) -shared -o $(LIBRARY) $(OBJECTS) $(LDPATH) $(LDLIBS)

clean: 
	rm -f $(OBJECTS) $(LIBRARY)

#eof "$Id: GNUmakefile,v 1.10 2008/04/17 20:06:34 rzr Exp $"
