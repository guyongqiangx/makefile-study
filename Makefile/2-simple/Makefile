all: main.o foo.o
	gcc -o simple.exe main.o foo.o

main.o: main.c
	gcc -o main.o -c main.c

foo.o: foo.c
	gcc -o foo.o -c foo.c

clean:
	rm simple.exe main.o foo.o
