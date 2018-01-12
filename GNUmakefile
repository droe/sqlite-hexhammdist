UNAME_S:=	$(shell uname -s)

ifeq ($(UNAME_S),Darwin)
SUFFIX:=	dylib
CFLAGS+=	-arch i386 -arch x86_64
else
SUFFIX:=	so
endif

CFLAGS+=	-fPIC
LIBS+=		-lsqlite3

all: sqlite-hexhammdist.$(SUFFIX)

sqlite-hexhammdist.$(SUFFIX): sqlite-hexhammdist.c GNUmakefile
	$(CC) -shared $(CFLAGS) -o $@ $< $(LIBS)

clean:
	rm -f sqlite-hexhammdist.$(SUFFIX)

