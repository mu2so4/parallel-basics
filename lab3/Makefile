CC=g++
CP=mpicxx
CFLAGS=-O3 -Wall -c

SERIES_SOURCE=series
PARALLEL_SOURCE=parallel

EXEC_EXT=out

all: $(SERIES_SOURCE).$(EXEC_EXT) $(PARALLEL_SOURCE).$(EXEC_EXT)

$(SERIES_SOURCE).$(EXEC_EXT): $(SERIES_SOURCE).o
	$(CC) $(SERIES_SOURCE).o -o $(SERIES_SOURCE).$(EXEC_EXT)

$(SERIES_SOURCE).o: $(SERIES_SOURCE).cpp
	$(CC) $(CFLAGS) $(SERIES_SOURCE).cpp -o $(SERIES_SOURCE).o



$(PARALLEL_SOURCE).$(EXEC_EXT): $(PARALLEL_SOURCE).o
	$(CP) $(PARALLEL_SOURCE).o -o $(PARALLEL_SOURCE).$(EXEC_EXT)

$(PARALLEL_SOURCE).o: $(PARALLEL_SOURCE).cpp
	$(CP) $(CFLAGS) $(PARALLEL_SOURCE).cpp -o $(PARALLEL_SOURCE).o

clean:
	rm -rf *.o
