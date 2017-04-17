SOURCES = ./trig/cos330.c ./trig/sin330.c ./trig/tan330.c ./exp/exp330.c ./exp/log330.c
OBJECTS = $(SOURCES:.c=.o)
CLI = ./cli/cli.c

top: $(CLI) lib $(OBJECTS) make_dirs 
	cp $(CLI) bin
	gcc ./bin/cli.c -I./include -L./lib -llibtrig
	

lib: $(OBJECTS)
	ar r libtrig.a $(OBJECTS)
	cp libtrig.a ./lib
	
	

$(OBJECTS): $(SOURCES) make_dirs
	gcc -c $(SOURCES) -I./include
	mv cos330.o trig
	mv sin330.o trig
	mv tan330.o trig
	mv exp330.o exp
	mv log330.o exp

make_dirs:
	mkdir -p ./include
	cp math330.h ./include
	mkdir -p ./lib
	mkdir -p ./bin

clean:
	rm -r ./include
	rm -r ./lib
	rm -r ./bin
	find . -type f -name '*.o' -delete
	rm libtrig.a
