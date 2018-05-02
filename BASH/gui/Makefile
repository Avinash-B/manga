TARGET = gui

SOURCES = gui.c lib.c

OBJECTS = $(subst .c,.o,$(SOURCES))

CC = gcc

$(TARGET): $(OBJECTS)
	$(CC) -g $(OBJECTS) -o $(TARGET) `pkg-config --cflags --libs gtk+-3.0 poppler-glib`

gui.o: gui.c lib.h gui.glade
	$(CC) -Wall -g -c -o $@ $< `pkg-config --cflags --libs gtk+-3.0 poppler-glib`

lib.o: lib.c lib.h
	$(CC) -Wall -g -c -o $@ $< `pkg-config --cflags --libs gtk+-3.0 poppler-glib`

.PHONY: clean
clean:
	-rm -f $(TARGET) $(OBJECTS)
