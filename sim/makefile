all:
	make clean; make compile; make simulate

compile:
	vlib work; 
	vlog -sv \
	+incdir+../src/hvl_top/env/virtual_sequencer/ \
  +incdir+../src/hvl_top/test/virtual_sequence/ \
	+incdir+../src/hvl_top/env \
	+incdir+../src/hvl_top/slave \
	+incdir+../src/hvl_top/test \
	+incdir+../src/hdl_top/slave_agent_bfm \
	+incdir+../src/hdl_top/spi_interface \
	../src/hvl_top/test/test_pkg.sv \
	../src/hvl_top/hvl_top.sv \
	../src/hdl_top/hdl_top.sv

simulate:
	vsim -novopt work.hvl_top work.hdl_top -c -do "log -r /*; add wave -r /*; run -all;" \
	-wlf waveform.wlf

clean:
	rm -rf work/ transcript vsim.wlf
