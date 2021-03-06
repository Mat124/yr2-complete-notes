# Combinatorial Logic

## Intro to Combinatorial

**Combinatorial Logic:** combines inputs in some way to generate an output without depending on any other factors (including previous inputs). For a given set of inputs there can be only one output.

Combinatorial circuits can have multiple layers, creating a hierarchy where there are sub-combinatorial elements:

![Hierarchical combinatorial circuit](hierarchical_combinatorial_circuit.png)

If there are any non-combinatorial elements, multiple nodes connected to the same input node or cyclic paths then the circuit is no longer combinatorial.

### Basic Boolean Algebra

- AND = ·
- OR = +
- XOR = ⊕
- NOT = ’

![Boolean Algebra Laws](boolean_algebra_laws.png)

**Karnaugh Maps:** Alternative to truth tables where adjacent cells differ in input values by only 1 bit, allows simplification of a logic expression by finding groupings in sizes of powers of 2:

![Karnaugh Map example](karnaugh_map.png)

Y = A’B’C’ + A’B’C + ABC’ + AB’C’ + AB’C is reduced to Y = AC’ + B’

Minterm: a distinct input array where the overall output can be defined as the sum of the minterms which result in an output of 1, e.g.

![sum of minterms](minterm_sum.png)

## Common Combinatorial Circuits

### Multiplexer (Mux)

Control signals decide which input should be connected to the output. Multiplexers can also be used to build logic functions by setting the inputs as constant and varying the control signals.

![4bit multiplexer](multiplexer_4bits.png)

![multiplexer as a logic function](multiplexer_as_logic_function.png)

### Decoders

Use k input bits to produce 2^k output bits where one is active (high/low) and the others are inactive (low/high). Useful for accessing memory addresses.

![decoder](decoder.png)

### Priority Encoder

Equal number of input and output bits where there is an order of priority for the input bits, and the output bit corresponds to the highest priority input that is active.

![priority encoder](priority_encoder.png)

![priority encoder truth table](priority_encoder_truthtable.png)

# Sequential Logic

## Intro to Sequential

**Sequential Logic:** inputs and memory are combined to create the output. Previous inputs affect the current output.

## Basic Sequential Circuits

### SR-type latch

The simplest circuit for storing one bit of data. Setting R high sets the output to 0, setting S high sets the output to 1, setting both high sets Q and Q' to 0, setting both low retains Q and Q' from the previous output.

![SR-latch](SR-latch.png)

Unpredictable behaviour occurs if both S and R are 1, then both are set to 0 at the same time. The output will be stable but is uncertain.

### D-type latch

This extends the SR-latch to fix the unpredictable behaviour by ensuring that R and S will have different inputs. Also introduces a CLK signal that controls when the output of the latch is updated.

![D-type latch](D-type_latch.png)

### Flip-flop

Made from 2 D-type latches linked together in the basic form. The output only changes to match D on the rising edge of the clock from 0 to 1 as while CLK = 1 the master D-type no longer changes its output to match D.

![flip flop](flip-flop.png)

Also drawn as:

![flip flop alt](flip-flop-alt.png)

### Registers

A bank of flip-flops with a common clock can act as a register to store multiple bits that can be accessed in parallel.

![register](register.png)

Shift-registers are a chain of flip-flops passing data from one to the next at each rising edge, and can be accessed in parallel or sequentially by reading only the final bit each clock.

![shift register](shift_register.png)

### FIFO Buffer

Formed by connecting whole registers in the shift-register pattern - a multibit input/output shift-register.

![FIFO_buffer](FIFO_buffer.png)

### Counters

Generates a sequence of outputs, typically a rising/falling sequence of binary numbers changing by 1 each time.

![counter](counter.png)

### Synchronous Memory

To store more data, multiple registers share an output data line. Addressing inputs signals allow different registers to be accessed and connected to the output data line. An address signal with N bits can differentiate between 2^N registers/memory locations using a decoder.

![Synchronous Memory](synchronous_memory.png)

![Synchronous memory with bits](memory_bit.png)

## Clocks

Oscillate between 0 and 1 at a fixed frequency. The period of the clock is the time to complete 1 cycle - the time between rising edges. The oscillations are often created using an external crystal oscillator. For low-level digital design there is typically a single clock in the system that all sequential components use. For more complex designs, there is a single source clock which is then used to generate multiple clock signals to allow for sequential circuits to have different frequencies.

# Verilog (combinational)

Verilog is a hardware description language - code which describes logical functions which are implemented using LUT in an FPGA. Designs are broken into modules, separate files that encapsulate some functionality. The modules can create instances of other modules for use within the module, with good designs having levels of hierarchy.

## Verilog Basics (structural)

**Identifiers:** Names of modules, signals, ports, registers, etc. They must start with a letter, can contain letters, numbers and underscores and can't be the same as a keyword.

### **Modules**

Each module is declared with the `module` keyword and a list of ports - the inputs/outputs to the module. Modules are instantiated using the module name, an identifier for that instance of the module and then the arguments. These are in the form `.x(y)` where `x` is the identifier in the module definition and `y` is the identifier being passed to the module.

![module instantiation](module_instantiation.png)

Modules can also contain parameters inside the definition or regular text. Parameters are constants local to the specific instance of a module and have default values that can be overridden on instantiation.

![module parameters](module_parameteers.png)

### **Gates**

The basic gates are inbuilt to verilog: `and`, `or`, `not`, `nand`, `not`, `xor`, `xnor`. These are called using their names, typically in the form:
`and andgate1 (outputwire1, inputwire1, inputwire2);`

Verilog multiplexer example:

![multiplexer verilog example](multiplexer_verilog.png)

### **Multibit Signals**

Inputs, outputs wires and registers can be multibit. These multibit signals are called vectors, and are defined by specifying a range of bits from MSB to LSB:

![multibit signal](multibit_vector.png)

By setting LSB above 0, the resolution of the signal is reduced, but can allow for a greater max value for the same about of bits. Vectors can also be indexed to select ranges/individual bits from the vector, e.g. `assign y = some[3]` sets `y` to the 4th from LSB bit of `some` and `assign z = some[4:3]` sets `z` to the 5th and 4th from LSB bits of `some`.

Vectors also allow assignments of mismatched vectors - e.g. a 4 bit wire is connected to a 2 bit wire. This does not produce any syntax errors and the left over bits are ignored or set to 0, but can produce logic errors.

### **Number Literals**

Constant numbers are specified in verilog using the format: \<`size`>'\<`radix`>\<`value`>. `size` is the amount of bits required to store the number in binary and `radix` refers to the numerical system used - `o` for octal, `b` for binary, `h` for hexadecimal, `d` for decimal. e.g.

- 4'b000 = 4 bits storing binary "0000"
- 8'h4F = 8 bits storing hex "4F" = 8 bits storing binary "01001111" = 8'b0100_1111 (underscores can be used for easier reading)
- 4'd11 = 4 bits storing decimal "11" = 4 bits storing binary "1011" = 4'b1011

### **Concatenation & Replication**

Concatenation is used to string together multiple signals into a single wider signal. This is done using `{}` enclosing a list of signals to be concatenated in the order they appear.

![concatenation](concatentation.png)     `b = a`<sub>`3`</sub>`a`<sub>`2`</sub>`a`<sub>`1`</sub>`a`<sub>`0`</sub>`0000`

Replication is used to copy signals and concatenate them to create wider signals, e.g. `4{a[3]} = a`<sub>`3`</sub>`a`<sub>`3`</sub>`a`<sub>`3`</sub>`a`<sub>`3`</sub>.

### **Assign**

**Assign:** The `assign` keyword is a continuous assignment where the result is a combinatorial function of the inputs - no clocks are necessary and it is simpler than using gate modules.

![assign keyword](assign_keyword.png)

This uses inline bitwise operators which are then simplified at compile time to the most efficient use of logic gates/LUTs, as well as allowing for basic arithmetic expressions:

- bitwise
  - `&` - and
  - `|` - or
  - `^` - xor
  - `~` - not (can be used in front of other bitwise operators, e.g. `~|` is nor)
- multibit
  - `+` - addition
  - `-` - subtraction
  - `*` - multiplication
  - `/` - division (can only be used in specific cases, isn't generally synthesizable)

**Conditional Assignments:** The same as a ternary operator in C, where a value is checked and assignment made based on that value.

![conditional assignment](conditional_assignment.png)

All general comparators work and are multibit, e.g. `<`, `>`, `>=`, `<=`, `==`, `!=`.

### **Primitives**

Verilog allows the creation of primitives, essentially custom logic gates. This is done used a truth table which defines the single output in relation to the inputs. The single output port must be the first port listed in the primitive description.

![primitive verilog](primitive_verilog.png)

### **Adders**

Simple half adder in Verilog:

![Half adder verilog](half_adder_verilog.png)

Full adder truth table and Verilog implementation using instantiated half adder:

![full adder truth table](full_adder_truthtable.png)

![full adder verilog](full_adder_verilog.png)

Full adder using `assign`:

~[adder using assign](adder_assign.png)

## **Behavioural Verilog**

Attempts to describe how the circuit behaves as opposed to directly defining the functions required. The implementation tools that interpret the Verilog code design hardware that fulfills the required behaviour. This can be combinational or or sequential.

### **`always` block**

An `always` block contains procedural (in order) or synchronous (not combinatorial) statements that are run when changes occur in specified signals - the sensitivity list. The identifier `*` is used to indicate the block should be rerun if there is a change in any signal used inside the input block.

Regular combinatorial statements, e.g. `assign`, cannot be used inside the always block.

![always block as a circuit component](always_block_as_logic_function.png)

**Registers `reg`:** signals assigned to from within always blocks are declared as `reg` and can be thought of similar to a variable. `reg`s cannot be used with the `assign` statement and also cannot be connected to regular `output` signals of a module - they must be labelled as `output reg`.

Equivalent assign and always blocks:

![equivalent assign and always blocks](equivalent_assign_always.png)

Verilog is concurrent in general - only code inside `always` blocks are procedural, where the ordering matters:

![concurrent vs procedural verilog](procedural_vs_concurrent_verilog.png)

In an always block, all outputs must be assigned to in all situations to make the block combinational, and no output can be used as input to the block. If this is not true, the block becomes sequential and a latch is created in logic as it implies that an output retains its value or a loop is formed. Having a sequential `always` block can be fine, but can slow down modules if having the `always` block combinational would've meant the entire module was combinational.

![sequential always](sequential_always.png) sequential->combinational ![combinational always](combinational_always.png)

### **Case Statements**

Same as regular case statements, syntax seen here:

![case statements](case_statements.png) - The issue is no assignment to z, making this block sequential and not combinational (this can be ok, just not what was wanted in this case).

Case statements can be used to simulate decoders, multiplexers and other logic functions:

![case decoder](case_decoder.png)

![case multiplexer and enable](case_multiplexer_and_enable.png)

# Sequential Verilog

Example D-type latch using a sequential verilog `always` block:

![sequential d-type latch verilog](sequential_verilog_dtype.png)

## Synchronous Verilog

Synchronous design in verilog allows for changes to be synchronised and allows the timing of the circuit to be more easily understood. Synchronising blocks can be done using a `clk` input to a module. By having `always` blocks triggered on the rising edge (`posedge`) of the `clk`, the outputs are of all blocks using `clk` updated at the same time - can be confusing if there are multiple `x_clk` signals for different blocks. `negedge` is the opposite of `posedge`, where the block triggers on the falling edge of the signal and by adding both `posedge` and `negedge`, the speed of execution can be doubled for the same clock signal (Double Data Rate (DDR)).\
![synchronous d-type](synchronous_d-type.png) - The sensitivity list only contains the `clk` signal and only updates when `clk` changes from 0 to 1.

The `<=` (called non-blocking) symbol is used instead of `=` (called blocking) to synchronise the changes inside the block - they are all made at the same time, not sequentially. This means that the code below would swap the values in `var1` and `var2` when inside an `always` block, instead of setting both to `var2` as would occur using `=`.\
`var1 <= var2` \
`var2 <= var1`

`clk` signals typically have a 50% duty cycle - half the time 1 and half the time 0.

### Registers

Registers are easy to set up in Verilog, example code is below. The `always` block represents 3 different registers - `q`, `r` and `s` - all of which share a `rst` signal and are clocked the same. The `clk` and `rst` signals in diagrams is not always drawn, and the `clk` signal can instead be assumed to be the same for all elements without one.\
![register verilog](registers_verilog.png)

### Reset signals (for registers)

**Asynchronous:** whenever the reset signal is asserted, the contents of the register is reset.\
![async reset](asynchronous_reset_verilog.png)

**Synchronous:** at a rising `clk` edge, if the reset signal is asserted then the register is reset (used in modern FPGAs).\
![sync reset](synchronous_reset_verilog.png)

## Standard synchronous components in Verilog

### Complex counters

An example of a complex counter that can load in values and both increment/decrement.\
![complex counter](complex_counter_verilog.png)

### Shift Registers

Example sequential read shift register, takes 4 clocks for the input to appear at the output: \
![shift register](shift_register_verilog.png) \
This could be changed to use a vector `q[2:0]` to store intermediate values more efficiently and allow the amount of intermediate latches to be extended easily. \
![efficient shift register](verilog_shift_register_efficient.png) - can be extended by changing the definition of `q` to include more bits and changing indices in the `always` block.

As with counters, shift registers can be extended to be more complex. This register has an enable signal `sh` and reverses direction if `rt` is high. \
![complex shift register](complex_shift_register.png)

### Parallel to serial conversion

A new k-bit word is fed in to the converter every k cycles when `ld` is asserted. Each subsequent cycle 1 bit is outputted from the k-bit word. \
![parallel to serial converter](parallel_to_serial_converter.png) ![parallel to serial verilog](parallel_to_serial_converter_verilog.png)

### FIFO Buffers

Multi-bit versions of shift registers, often used for creating delay lines. \
![4bit fifo buffer](4bit_fifo_buffer.png)

### Simple memory

Cells are created using `reg` in Verilog. `reg [X:0] ram [0:Y]` creates Y+1 cells that store X+1 bits that can be accessed using `ram[0<=N<=Y]` to access the X+1 bits stored at address N. \
![simple memory](simple_memory_verilog.png)

## What is synthesised from an always block?

All assignments made create registers on the FPGA. These are then linked together with combinational elements to create the required outputs. A synchronous `always` block can be broken into direct assignments to registers and combinational circuits. \
![synchronous always block](always_block_synthesis.png)

# Verilog Arithmetic

FPGAs are used primarily for complex computation applications with high data throughput, large arithmetic operations and parallel processing requirements. Design tools take care of many implementation details, but the designer is responsible for: decomposing complex expressions into synthesisable operands, managing registers to optimise performance, aligning and interpreting fixed point arithmetic, manual floating point operations, etc.

## Binary

I'm not explaining how to do basic binary. Signed numbers can be represented using 'sign-magnitude' where the first bit indicates + or -, or 'two's complement' where the first bit has negative weight. Two's complement is the most important and most used one.

## Adders

Basic adders have already been seen, look above.

### Ripple adders

Multiple full adders chained together so that the carry signal propagates down the line of adders. Each adder must wait until the previous adder is done as otherwise an incorrect output could be read - hence the values 'ripple' down the adders.\
![ripple adder](ripple_adder.png)

Ripple adders can be adapted to be able to subtract numbers. The operand being subtracted is inverted using XOR gates and 1 is added using the first adders carry in. \
![subtracting ripple adder](subtracting_ripple_adder.png)

Ripple adders can only be clocked as fast as the signal can propagate down the critical path - in the case of ripple adders this is from carry in of the first adder to carry out of the last adder. This means that large bit ripple adders are clocked slowly in comparison to smaller adders - inefficient.

### Carry-lookahead adders

Carry-lookahead adders attempt to fix the issue of propagation delay in ripple adders. This is done by introducing two more signals at each stage: *generate* and *propogate*. *generate* is true if the stage will be produce a carry no matter what the carry in is, i.e. both operands are 1. *propogate* is true if the stage produces a carry if carry in is 1, i.e. either/both operands are 1. \
For stage i: \
g<sub>i</sub>=a<sub>i</sub>&b<sub>i</sub> \
p<sub>i</sub>=a<sub>i</sub>|b<sub>i</sub> \
Therefore, the carry out of stage i is: co<sub>i</sub>=g<sub>i</sub>|(p<sub>i</sub>&ci<sub>i</sub>) \
![carry lookahead adder 4bit](carry_lookahead_adder_4bit.png)

We can use this to calculate the carry out at any stage using the propagate/generate signals from the previous stages: \
![carry lookahead calc](carry_lookahead_calculation.png)

Logic to calculate the carry bits can then be implemented. This means that the delay from the first carry in to carry out is reduced from going through all adder units to a single adder unit (all of them finish in parallel) and the delay from the lookahead carry unit. \
![lookahead carry unit 4 adders](lookahead_carry_unit_4_adders.png)

Smaller carry lookahead adders are combined to make larger ones, as the circuitry for >4 bit lookahead carry units become very complex. Combining 4 carry lookahead adders of 4 bits with a 4-bit lookahead carry unit creates a 16-bit carry lookahead adder. \
![carry lookahead adder 16bit](carry_lookahead_adder_16bit.png)

### FPGA adders

Carry logic in an FPGA typically mimics a carry lookahead adder.

- *S*: propagate signals
- *DI*: generate signals
- *CYINIT*: first carry in
- *O*: outputs
- *CO*: carry outs for each bit

![FPGA adder](FPGA_carry_adder.png)

## Multipliers

Binary multiplication is done similar to decimal long multiplication: moving the starting point further above the base depending on the place of the multiplying bit, then multiplying each bit in the other number by the multiplying bit: \
![binary multiplication](binary_multiplication.png)

Multiplication in circuits can be done using long chains of adders. The inputs to the adders are the partial products of the multiplication numbers: e.g. S<sub>50</sub> = A<sub>5</sub>&B<sub>0</sub>. \
![fpga multipliers](FPGA_multipliers.png) \
This type of multiplication has extremely long propagation delays. This can be fixed in FPGAs by using LUTs that are prefilled with outputs instead of using adder chains. Wide multiplications too large for LUTs are mapped to DSP blocks, or multiple DSP blocks as these are designed for efficient multiplication.

## Fixed point binary

A binary point is placed at a fixed location within the number - powers of 2 to the left of the point start at 0 and increase (integer section), powers of 2 to the right of the point start at -1 and decrease (fractional section). \
![fixed point binary](fixed_point_binary.png) \
There is no fixed notation for stating the position of the binary point, so words are used to express the format. Fixed point binary can also be signed, where the first bit has negative weight. Only certain numbers can be expressed exactly in a given fixed point format, so this introduces some error to calculations using fixed point that can be minimised by selecting an appropriate format.

The integer section determines range, e.g. 4 int bits give a range of 0-15, and the fraction section determines precision, e.g. 6 fractional bits can represent values to 2<sup>-6</sup> = 0.015625. Changing the distribution of integer to fractional bits allows greater range or precision for the same total bits.

Addition/Subtraction: binary point stays where it is, may need extra bit for overflow \
Multiplication: multiplying an *m*-bit number with *n* fractional bits by a *k*-bit number with *j* fractional bits gives an *m+k* bit number with *n+j* fractional bits. \
**it is very important to keep track of where the integer and fractional parts are**

### Decimal to fixed point conversion

1) Multiply the number by 2<sup>I</sup> where *I* is the number of fractional bits
2) Round the result to an integer
3) Convert the integer to binary in the standard way
4) Use the binary representation of that number as the fixed point representation, remembering the position of the binary point

### Fixed point in Verilog

Verilog doesn't support fixed point natively, instead the programmer must keep track of the binary point positions. Vector slicing can then be used to choose the correct bits. Most numbers in verilog are treated as unsigned regular binary, and the binary operations act as though performed on numbers in that format.

## Signed arithmetic in Verilog

The `signed` keyword is put after wire/reg and before the identifier to indicate the signal is signed, allowing for negative number representation. \
![signed nums verilog](signed_numbers_verilog.png) \
When arithmetic is applied to the signals, signed circuits will be used. However, if any operand (including output) in an operation is unsigned the arithmetic circuit used will be unsigned, which could lead to an incorrect output. Verilog automatically does sign-extension for signed signals, which can lead to unexpected results. \
![sign extension verilog](sign_extension_verilog.png) \
In the case above, the 8 bit number inputted to the `max_val` reg is assumed to be signed - giving it negative value, so the preceding bits are set to 1 to keep the value the same. In the case where the MSB of the input was 0, the preceding bits would also be set to 0.

The functions `$signed()` and `$unsigned()` can cast numbers to signed/unsigned. This is not done intelligently however, so if the MSB of an unsigned number is 1 and it is cast to signed, the output will be negative. The same goes for casting a negative signed number to unsigned - the output will not be accurate as it cannot be represented. \
![signed casting verilog](signed_casting_verilog.png) \
Unsigned numbers should always be 0 extended to ensure they do not become negative to avoid accidental incorrect casting.

Signed numbers in verilog can be truncated from the MSB down until the 2nd MSB is different from the MSB, e.g.: \
![signed truncated numbers](truncated_signed_numbers.png)

**Verilog will create warnings for truncated numbers, but will still synthesis without errors.**

## Floating point numbers (IEEE-754)

32-bit numbers consisting of a sign bit, 8 exponent bits and 23 mantissa bits. This number then has the value: (-1)<sup>sign</sup> * mantissa * 2<sup>exponent-127</sup>. Not all numbers can be accurately represented. \
![floating point](floating_point_representation.png)

This can be thought of as the exponent determining which powers of two the window covers: e.g. between [1, 2], [2, 4], [4, 8], ..., [2<sup>20</sup>, 2<sup>21</sup>], etc. The mantissas determines where in the window the number is. Larger exponents mean that the mantissa covers a greater range with the same amount of bits - less accurate.

Floating point arithmetic circuits are large and complicated, each computation can require realignment of operands, arithmetic and normalisation. There is no direct support for floating point calculations in Verilog, but IP blocks exist to allow for it. However, floating point calculations are not often needed.

# Verilog Verification and Testing

Types of verification:

- **Algorithmic verification:** is the chosen algorithm suitable for the desired application implementation in FPGA - does the algorithm work in other software
- **Functional verification:** ensure the designed architecture correctly implements the algorithm - e.g. do shift registers work the same way in the FPGA as simulated?
- **Synthesis verification:** ensure the design is fully synthesisable and implementable on the desired target platform - is there enough LUTs on the FPGA to implement this?
- **Timing verification:** once synthesised, placed, etc, are the timing requirements met to reach the desired clock speeds?

Errors in design:

- specification is wrong/incomplete, so design meets specification but does not achieve what is required to function in use
- specification can be misinterpreted, so the design meets what you believe the specification means as opposed to what the specification actually means
- the specification is correctly understood, but the design has logic errors that mean it does not meet it

## Testbenches

A self-contained module typically without inputs/outputs. The module instantiates the unit under test (UUT) and contains a number of blocks that interact with that unit to ensure it functions correctly: clock generators, data/control signal generators and data/status signal monitors. \
![testbench diagram](testbench_diagram.png) \
The drivers creates values that can be expected to be seen in real use to generate outputs that match what is expected. If the outputs of the unit under test are correct, we can assume that the unit under test functions as expected.

Testbench inputs and outputs to the unit under test are generated using `reg` for inputs and `wire` for outputs. \
![testbench input output](testbench_input_output.png)

Waiting can be achieved using `#X` to wait X timesteps (defined in the testbench settings) before executing the statement. These cannot be synthesised and can only be used in testbenches.

**`initial` block:** Can only be used in testbenches - cannot be synthesised. Similar layout to an `always` block, but is only run once at startup to give initial values to connections.

### Displaying data

The simulator has a console where text messages can be printed by the testbench. This is done using the `$display` and `$write` (no newline) commands in the same format as C style `printf`. Values from registers can be written to the console using the format: \
`%b` - display number in binary format \
`%h` - display number in hexidecimal format \
`%d` - display number in decimal format \
e.g. `$display("The value from register a in decimal and binary is: %d %b", a, a)` would display the value of a in decimal and binary formats. This would include leading 0s, the amount register a could contain, e.g. if a has 16 bits, there will be 16 digits.

**Value change dump:** dump file that some simulators require that can then be viewed later. the `.vcd` or value change dump format is used. Dump file is set using `$dumpfile("dumpfile.vcd")` and then values are set in the file using `$dumpvars(1, modulename)` to dump all signals in list or in named modules, or `$dumpvars(0, modulename)` to dump all signals in named modules and their children.

### Verifying combinational modules

Can be done by simulating all the possible inputs and checking the outputs against manually calculated expected values - this becomes impossible for more than 3/4 inputs with 1/2 outputs due to amount of different calculations needed.\
Self checking testbenches calculate the correct outputs by essentially doing the same thing as the module is supposed to. This means there isn't a need for manual calculations, but can cause issues if the testbench contains logic errors or accidental code errors. The inputs to the module can be generated using a counter and assigning signals to different sections of the counter, e.g. \
![counter verification](counter_comb_verification.png)

### Verifying synchronous modules

Sychronous modules require clocks. These can be generated by testbenches using `always` blocks and delays. The timescale of testbenches are specified at the top of the source file, outside the testbench module using the command `timescale`, e.g. `timescale 1ns / 100 ps` to set a time unit of 1ns and a rounding precision of 100ps. Round is used when doing partial time steps, e.g. `#123/100` would give 1.2ns delay instead of 1.23ns as the round only goes to 100ps using the above timescale.

### More Techniques

The set of inputs driving the module being tested is the **test vector** and can be loaded in from external files, allowing for test data generation to be automated instead of manual. This is done using C commands: creating a file handle with `$fopen` and scanning in data using `$fscanf`. \
![Verilog files](verilog_files.png) \
This opens the file in read mode, then reads a hex value to data and binary value to mode every clock edge.

This allows for the creation of self-checking testbenches that can read in input data and expected output data generated using other programs from external files, then check the actual module outputs against the expected output when given the inputs.

## Advanced Verification and other testing things

Other system functions can be very useful, e.g. `$random` to generate random numbers.

Corner cases are good to focus on if there are too many input possibilities to test thoroughly. 

Finite state machines can be tested easily by decomposing them into combinational state transition logic and then testing as a whole state machine.

Software models - good for prototyping possible solutions to thee design specification. Can be done at several layers: **simple model** without respect for hardware implementation/design; **model that mimics the overall function** of the hardware implementation/design; **a cycle-accurate model**, matching the hardware implementation/design to the clock cycle; **bit-accurate model** where all functions and arithmetic are done at same precision as model, as well as being cycle-accurate. \
Differences can occur between a functionally correct circuit and a software model due to differences in number representation, calculation order/methods and rounding errors. These can cause tests to fail when the module is correct if not accounted for, so these discrepancies must be known and allowed for, e.g. by allowing the module output to be in a range of the software model output.

Another way to verify the outputs of a module is to perform the inverse functions on the output (if it exists) using external software and comparing this to the inputs given to the module. This works for functions like mathematical transforms, encryption/decryption, encoding/decoding, etc.

### Simulation environments

Useful for testing simple modules to give quick results. Provides a wave viewer that shows the values of each signal/register in the module (or just select ones) that can be used to see the results, but is insufficient for good module verification.

### Modern Verification difficulties

Verification of very complex designs, e.g. large multi-processor system-on-chip with some hardware accelerators, are very difficult. Requires:

- Testing ach processor and all layers in hierarchy
- Testing communication infrastructure between units
- Testing contention for resources - behaviour of system under stress
- Predicting effects of scenarios like cache misses

Testing during design can help to reduce amount of testing required and make testing easier. Means that less time will be needed fixing large logic errors after the full system is designed and no previous parts need to be completely changed.

# Finite state machines

## Sequence and States

At each point in time, an FSM is in a **state** - the current values/description of the system. The system can then transition between states depending on **conditions**. \
![adder fsm](adder_fsm.png) \
Above is the state transition diagram of a basic 3 bit adder that loops. Each node is a **unique state** of the system and arrows show movement from one state to the next - there cannot be multiple nodes representing the same state.

State transitions (**edges**) can have **conditions**, e.g. if an input is on or not, and be set to occur with a clock. \
![enable adder fsm](enable_adder_FSM.png) \
Loop edges are not always included - the diagram could instead show only the `en` condition transitions and it is implied that nothing happens (or it loops back to the same state) when `en` is not high.

Example up/down adder using inputs `en` and `dn` in that order - conditions then show the values of the inputs. \
![up/down adder](up_down_adder_FSM.png) \
State names and outputs are given in the form `name/output` in most FSM (but not the ones shown so far).

In synchronous design, the **FSM is in one state for the duration of each clock cycle and may transition at each rising clock edge**.

### State tables

State transition information can be represented in tables, effectively a truth table for the next state based on current state and inputs. \
![state table](state_table.png) \
This table represents the following FSM. \
![state table FSM](state_table_FSM.png)

## Mealy machines

The FSMs seen so far are **Moore Machines** - the output only depends on the state. **Mealy Machines** have outputs that depends on the state and current value of the inputs - the outputs can change mid-state if the inputs change. This allows for more complex FSMs to be created without adding many more states, at the cost of them being harder to design and analyse.

Mealy machines have the outputs on the arrows after a slash after the inputs that caused the change. An example of a Mealy machine implementing the output of x=1 3 times after b=1 once: \
![mealy machine simple](mealy_machine_simple.png)

Both the below FSMs have the same function: outputs a 1 when the last two inputs were 0,1 in that order: \
![moore vs mealy](moore_vs_mealy_fsm.png)

## Basic Implementation

Using a state table, a combinatorial circuit that determines the next state from current state and inputs can be built. A register holds the current state and another combinatorial circuit can be built that creates the correct output given the current state. \
![implementing fsm](implementing_fsm.png)

The general implementation of a FSM changes depending on whether it is Moore or Mealy: \
![moore mealy FSM iomplementation](moore_mealy_FSM_implementation.png)

### State Encoding

State encoding in verilog is used to store the current state in a binary register as opposed to using state names. A unique binary value is assigned to each state (this can be done using **parameters**), so a *m* state machine requires log<sub>2</sub>(m) bits. For 8 states, a register `reg [2:0] s` could be used.

### Transition Logic

State transition logic can be implemented using logic gates. Given a FSM with 4 states, the current state stored in `[1:0]s` and the next state stored in `[1:0]ns` we can construct logic which matches the state table: \
![state transition logic](state_transition_logic.png) \
This can be done by inspection, or using a karnough map or similar method.

The verilog implementation of the FSM described by the above state table is: \
![verilog fsm iomplememntation](verilog_fsm_implementation.png) \
The `always` block updates the state register with the next state value, and combinational assignments handle finding the next state value and output.

Ensure that a FSM **always has a reset and valid initial state**. If this is missing, the FSM may start in an invalid state and won't act predictably.

## Complex FSM Implementation

For FSMs with many states and inputs, e.g. 6 states and 5 inputs, behavioural verilog can be used instead of combinational logic to make the designer's job easier. States are encoded the same way as before and the state transition can still occur inside a clocked `always` block as before. This general structure is shown below: \
![general FSM implementaiton](general_fsm_implementation.png)

The next state logic is then implemented using `case` and `if` statements. This is faster to design than attempting to derive combinational logic for the state transition, and the synthesis tools in verilog will make similarly efficient implementations. The output logic can also be designed using behavioural verilog, inside the same always block as state logic. \
![verilog behavioural state transitions](verilog_behavioural_state_transitions.png) \
The verilog shows example behavioural code for state transitions of the lock from earlier, where the correct sequence of coloured buttons must be pressed.

### Complex FSM Implementation other notes

- Possible to write the whole FSM in a single synchronous `always` block - hard to verify so easier to use multiple.
- **ensure that resets change the state register to a valid state**
- A next state must be assigned in every case - undefined behaviour will arise if not
- default next state/output assignment at the top of the state transition block can help minimise the number of statements

# FPGAs

Everything designed using a HDL (like verilog) is built out of basic circuit components, which are eventually built of transistors.

## ASICs vs FPGAs

### ASICs

Design is built using specific circuit components using a fabrication process. Masks are created by the tools which are then used to layer and etch the circuit boards.

- high startup costs, masks alone from $100k-1M
- detailed design effort to optimise performance (specific sizes of components and tolerances etc)
- significant risk if design has errors: could require completely new mask
- cant modify design without new mask
- low production costs once started

### FPGA

Reprogrammable, uses LUT (look up tables) to simulate a lot of circuit components, as well as having other general circuitry. 

- low startup costs, as general boards dont have to be custom made
- high cost per board compared to ASICs
- easily reprogrammable and good for prototyping

### Cost tradeoffs

![fpga asic costs](fpga_asic_costs.png)

## FPGA Architecture

A flexible chip that can implement many different circuits. Knowledge of the low-level implementation of FPGAs are essential to achieve very efficient designs.

FPGAs contain 4 distinct types of resource that allow them to implement many different circuits:

- **flexible logic:** basic configurable blocks (CLBs) to implement comb logic with clocked elements for synch logic and pipelining
- **flexible routing:** large chip area dedicated to wires/switch boxes to enable connections between different components
- **flexible IO:** multi-standard interfacing to external pins, range of clocking capabilities
- **embedded hard modules:** number of different resources with specific purpose, e.g. DSP functions, high-speed memory

example FPGA chip architecture: \
![general fpga architecure](FPGA_example_architecture.png)

### CLBs (Configurable Logic Blocks)

These implement almost all computations required on FPGAs. They consist of a LUT to do combinational functions, some auxiliary arithmetic logic and a flip-flop for synchronous logic. \
![CLB structure](CLB_structure.png)

### Xilinx Logic Architecture

LUTs grouped in 4s, called slices. These slices contain LUTs, clocked elements (like flip-flops) and arithmetic logic. The pieces can be used individually or together depending on what needs to be done. These slices are then grouped together to form a CLB with a hierarchy of connections. \
![xilinx clb](xilinx_clb.png)

### LUTs

An n-input LUT is a 2<sup>n</sup> x 1 bit memory block. The truth table of the logic function implemented is stored in the LUT: an input to the LUT is the memory location that stores the corresponding output. The propagation delay of the LUT is constant, not affected by the function it computes.

![lut logic function](lut_logic_function.png) \
The function above has it's truth table computed at synthesis, which is then stored in a LUT when written to an FPGA instead of attempting to simulate gates.

Modern LUTs have 6 inputs, giving 64 memory locations. This can be used to implement a single 6-input function, 2 x 5-input (all shared) functions, 2 x 3-input (all independent) functions, etc. LUTs can also be combined to form 7+ input functions.

As LUTs are memory blocks, they can act as *distributed RAM*. This is synchronous write and can be used with the flip-flops in CLBs to create synchronous read, improving timing. Multiple RAM configurations can be achieved: 64x1bit single port using 1 LUT, 64x1bit dual port or 128x1bit single port using 2 LUTs, etc.

### Routing

Large grids of wires run throughout the FPGA. Connection boxes allow different elements to connect to this network. Switch boxes connect different tracks together to form working connections between elements.

Routing affects performance of a system by reducing the maximum clock frequency as the amount of switch boxes used increases. Dedicated wires between blocks are faster, but more specific and can't be used everywhere due to size. Individual bits of a multi-bit signal can take different routes, in which case the worst case matters most. Different lengths of wire in different directions are used to help improve performance, changing the pattern of amount of switches between blocks: \
![routing switches](routing_switches.png)

### IO

FPGAs have flexible IO: individual groups/banks of pins can be interfaced with using multiple different standards set during design (usually done by IP blocks). As well as bare pins, FPGA boards can sometimes have physical ports for standards like ethernet, SATA, PCIe, etc. IP blocks are still required to configure them, but allows for easier physical connections.

### Block Memory

LUTs can act as RAM, but dedicated block RAM is also typically provided in FPGAs. These can be simple dual port (dedicated read/write) or true dual port (both can perform read/write). Multiple blocks of RAM can be combined to form a larger RAM section. This RAM can have different widths/clocks for each port and has a standard speed of 10s Mbits.

### DSP blocks

FPGAs contain hardwired DSP blocks, suitable for multiply/add operations and much faster than LUTs. While hardwired, they are still configurable and can change pipeline stages, ALU functionality, introduce bypasses, combine with other DSP for cascading signals, do pattern recognition, etc.

# Digital Design Flow

Process by which we specify and design a digital system through to final implementation. 