.PHONY : all clean rebuild test-prefetch

all: ssd
	
clean:
	rm -f ssd *.o *~

ssd: ssd.o flash.o  pagemap.o  hash.o   initialize.o
	gcc  -g -o ssd $^ -lm
%.o: %.c initialize.h flash.h pagemap.h ssd.h hash.h
	gcc -c  -g  $< -o $@

test-prefetch:
	python3 tests/run_prefetch_stats.py

rebuild : clean all
