# VHDL Process Sensitivity List Error

This repository demonstrates a common error in VHDL: an incomplete sensitivity list in a process.  The code in `bug.vhd` contains a process that only has the clock signal (`clk`) in its sensitivity list.  This will lead to unexpected behavior if `data_in` changes without a clock edge.   The solution in `bugSolution.vhd` corrects this by adding `data_in` to the sensitivity list, ensuring that the process updates `data_out` whenever `data_in` changes, regardless of clock events.

## How to Reproduce
1. Simulate the `bug.vhd` code. Observe the incorrect output when `data_in` changes asynchronously to the clock. 
2. Simulate the `bugSolution.vhd` code. Observe the correct output when `data_in` changes.

## Lesson Learned
Always carefully check the sensitivity list in your VHDL processes.  A missing signal can lead to subtle and difficult-to-debug errors.