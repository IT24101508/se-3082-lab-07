CC = mpicc
CFLAGS = -O2

PROGRAMS = program sum_scatter sum_gather sum_reduce sum_allreduce sum_scan

all: $(PROGRAMS)

program: program.c
	$(CC) $(CFLAGS) program.c -o program

sum_scatter: sum_scatter.c
	$(CC) $(CFLAGS) sum_scatter.c -o sum_scatter

sum_gather: sum_gather.c
	$(CC) $(CFLAGS) sum_gather.c -o sum_gather

sum_reduce: sum_reduce.c
	$(CC) $(CFLAGS) sum_reduce.c -o sum_reduce

sum_allreduce: sum_allreduce.c
	$(CC) $(CFLAGS) sum_allreduce.c -o sum_allreduce

sum_scan: sum_scan.c
	$(CC) $(CFLAGS) sum_scan.c -o sum_scan

run: all
	mpirun -np 4 ./program
	mpirun -np 4 ./sum_scatter
	mpirun -np 4 ./sum_gather
	mpirun -np 4 ./sum_reduce
	mpirun -np 4 ./sum_allreduce
	mpirun -np 4 ./sum_scan

clean:
	rm -f $(PROGRAMS)
