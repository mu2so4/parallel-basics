CXX=g++
CXXP=mpicxx
CFLAGS=-c -std=c++11 -O3 -Wall

FIELD_SOURCE=field
LIFE_SOURCE=life
LIFE_BLOCKED_SOURCE=life_blocked

EXEC_EXT=out

all: $(LIFE_SOURCE).$(EXEC_EXT)

$(LIFE_SOURCE).$(EXEC_EXT): $(LIFE_SOURCE).o $(FIELD_SOURCE).o
	$(CXXP) $(LIFE_SOURCE).o $(FIELD_SOURCE).o -o $(LIFE_SOURCE).$(EXEC_EXT)

$(LIFE_SOURCE).o: $(LIFE_SOURCE).cpp $(FIELD_SOURCE).h
	$(CXXP) $(CFLAGS) $(LIFE_SOURCE).cpp -o $(LIFE_SOURCE).o

$(LIFE_BLOCKED_SOURCE): $(LIFE_BLOCKED_SOURCE).o $(FIELD_SOURCE).o
	$(CXXP) $(LIFE_BLOCKED_SOURCE).o $(FIELD_SOURCE).o -o $(LIFE_BLOCKED_SOURCE)

$(LIFE_BLOCKED_SOURCE).o: $(LIFE_BLOCKED_SOURCE).cpp $(FIELD_SOURCE).h
	$(CXXP) $(CFLAGS) $(LIFE_BLOCKED_SOURCE).cpp -o $(LIFE_BLOCKED_SOURCE).o

$(FIELD_SOURCE).o: $(FIELD_SOURCE).cpp $(FIELD_SOURCE).h
	$(CXX) $(CFLAGS) $(FIELD_SOURCE).cpp -o $(FIELD_SOURCE).o

clean:
	rm -rf *.o
