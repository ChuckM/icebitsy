#
# Simplest start, lets figure out what a 'Platform' is in Litex.
#
DESIGN=blink

#
# Linux version of the DFU utility
#
PROG = dfu-util
#
# Windows version of the DFU utility.
# Use this if you're building this under WSL. 
#
#PROG = dfu-util-static.exe

$(DESIGN).bin:	build/top.bin
	cp $< $@

build/top.bin: $(DESIGN).py
	./$(DESIGN).py

flash: $(DESIGN).bin
	$(PROG) -d 1d50:6146 -a 0 -R -D $<

clean:
	rm -rf build $(DESIGN).bin
