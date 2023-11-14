CC = gcc
SRC = src/
CFLAGS = -fopenmp -Ofast -march=native -fno-signed-zeros -ffp-contract=fast -ftree-vectorize -mavx

.DEFAULT_GOAL = all

all: MDpar.exe MDseq.exe

MDpar.exe: $(SRC)/MDpar.cpp
	module load gcc/11.2.0;
	$(CC) $(CFLAGS) $(SRC)MDpar.cpp -lm -fopenmp -o MDpar.exe

MDseq.exe: $(SRC)/MDseq.cpp
	module load gcc/11.2.0;
	$(CC) $(CFLAGS) $(SRC)MDseq.cpp -lm -fopenmp -o MDseq.exe

clean:
	rm ./MD*.exe

runseq:
	./MDseq.exe < inputdata.txt

runpar:
	./MDpar.exe < inputdata.txt
