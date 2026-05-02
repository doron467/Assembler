CC = gcc
CFLAGS = -ansi -pedantic -Wall
OBJECTS = assembler.o secondpass.o firstpass.o preprocessor.o symbols_table.o memory_image.o utils.o
HEADERS = memory_image.h symbols_table.h preprocessor.h utils.h constants.h

all: assembler

assembler: $(OBJECTS)
	$(CC) $(CFLAGS) $(OBJECTS) -o assembler

assembler.o: assembler.c preprocessor.h firstpass.h utils.h
	$(CC) $(CFLAGS) -c assembler.c -o assembler.o

secondpass.o: secondpass.c secondpass.h firstpass.h $(HEADERS)
	$(CC) $(CFLAGS) -c secondpass.c -o secondpass.o

firstpass.o: firstpass.c firstpass.h $(HEADERS)
	$(CC) $(CFLAGS) -c firstpass.c -o firstpass.o

preprocessor.o: preprocessor.c preprocessor.h utils.h constants.h
	$(CC) $(CFLAGS) -c preprocessor.c -o preprocessor.o

symbols_table.o: symbols_table.c symbols_table.h preprocessor.h utils.h constants.h
	$(CC) $(CFLAGS) -c symbols_table.c -o symbols_table.o

memory_image.o: memory_image.c memory_image.h utils.h constants.h
	$(CC) $(CFLAGS) -c memory_image.c -o memory_image.o

utils.o: utils.c utils.h constants.h
	$(CC) $(CFLAGS) -c utils.c -o utils.o

clean:
	rm *.o
