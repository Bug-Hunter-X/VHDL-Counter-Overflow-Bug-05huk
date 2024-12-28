# VHDL Counter Overflow Bug

This repository demonstrates a common but subtle error in VHDL code: an integer counter that lacks proper overflow handling. The `buggy_counter.vhd` file contains the faulty code, while `fixed_counter.vhd` provides the corrected version.

## The Bug

The `buggy_counter` entity is designed to count from 0 to 15. However, when it reaches 15, the next increment results in an overflow. While VHDL might not explicitly throw an error, the behavior after overflow is undefined and can lead to unpredictable results in simulation or hardware implementation. This subtle bug can be very hard to detect and debug.

## The Solution

The `fixed_counter` entity addresses this issue by adding a check for overflow.  When the counter reaches 15, it resets to 0 instead of overflowing.  This ensures predictable and correct behavior.

## How to Reproduce

1.  Simulate `buggy_counter.vhd` and observe the behavior when the counter goes beyond 15.
2. Simulate `fixed_counter.vhd` and verify the corrected behavior.

This example highlights the importance of careful consideration of data types and range limits when writing VHDL code.