CC=icc -Wall

SSE=-mmic

DEBUG=-g

CFLAGS = -O3 -I. $(SSE) -mkl -pthread -mcmodel=medium -std=c++0x $(DEBUG)

LIBS = -lpthread -mkl -L$(MKLROOT)/lib/mic

LDFLAGS = $(SSE) $(LIBS) $(DEBUG)

SRCS = $(wildcard ./*.cpp) $(wildcard ./*.c)

$(info $(SRCS))

OBJS = $(SRCS:.cpp=.o)

main: $(OBJS) $(wildcard ./*.h)
	$(CC) $(LIBS) $(LDFLAGS) -o main $(OBJS)
%.o : %.cpp
	$(CC) $(CFLAGS) -c $< -o $*.o

clean:
	-rm main $(OBJS)
