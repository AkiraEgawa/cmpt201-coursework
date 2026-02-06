CC = clang
EXECUTABLE = lab3

all: $(EXECUTABLE)

%: %.o
	$(CC) $< -o $@

%.o: %.c
	$(CC) -c $< -o $@

clean:
	rm -f %.o $(EXECUTABLE)
