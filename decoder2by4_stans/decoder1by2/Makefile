GTKWAVE:=$(which gtkwave)

all: decoder

decoder:prerequisites
	@echo 'building file $(@F)'
	$(CXX) -I/usr/local/systemc-2.3.2/include -O0 -g3 -Wall -c decoder_1by2.cc
	$(CXX) -L/usr/local/systemc-2.3.2/lib-linux64 -o "decoder" decoder_1by2.o -lsystemc
	./decoder
	gtkwave -c 4 timing_diagram.vcd

prerequisites: 
ifneq "$(GTKWAVE)" "/usr/bin/gtkwave"
	@echo 'installing gtkwave, please be patient'
	sudo apt-get install -y gtkwave
endif

clean:
	rm -f decoder *.o timing_diagram.vcd
.PHONY: decoder
