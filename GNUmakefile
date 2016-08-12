all: sqlite-hexhammdist.so

sqlite-hexhammdist.so: sqlite-hexhammdist.c GNUmakefile
	$(CC) -shared -fPIC -o $@ $< -lsqlite3

clean:
	rm -f sqlite-hexhammdist.so

