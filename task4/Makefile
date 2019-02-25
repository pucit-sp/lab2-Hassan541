all: myapp
CC=gcc
CFLAGS= -std=c11 -O0 -Wall -g
INCLUDES=.
LIBS = -lc
OBJS=driver.o prog1.o prog2.o prog3.o prog4.o
INSTDIR = /usr/bin
myapp: $(OBJS)
	$(CC) -o myapp $(OBJS) $(LIBS)
driver.o: driver.c header.h
	$(CC) -c driver.c -I$(INCLUDES) $(CFLAGS)
prog1.o: prog1.c
	$(CC) -c prog1.c $(CFLAGS)
prog2.o: prog2.c
	$(CC) -c prog2.c $(CFLAGS)
prog3.o: prog3.c
	$(CC) -c prog3.c $(CFLAGS)
prog4.o: prog4.c
	$(CC) -c prog4.c $(CFLAGS)

include:

clean:
	 @rm -f $(OBJS)

install: myapp
	@if [ -d $(INSTDIR) ]; \
	then \
		cp myapp $(INSTDIR) && \
		chmod a+x $(INSTDIR)/myapp && \
		chmod og-w $(INSTDIR)/myapp && \
		echo "myapp installed successfully in $(INSTDIR)"; \
	fi

uninstall:
	@rm -f $(INSTDIR)/myapp
	@echo "myapp successfully un-installed from $(INSTDIR)"

