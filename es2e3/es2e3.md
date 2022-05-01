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

# Verilog

Verilog is a hardware description language - code which describes logical functions which are implemented using LUT in an FPGA. Designs are broken into modules, separate files that encapsulate some functionality. The modules can create instances of other modules for use within the module, with good designs having levels of hierarchy.

## Verilog Basics (structural)

**Identifiers:** Names of modules, signals, ports, registers, etc. They must start with a letter, can contain letters, numbers and underscores and can't be the same as a keyword.

### Modules

Each module is declared with the `module` keyword and a list of ports - the inputs/outputs to the module. Modules are instantiated using the module name, an identifier for that instance of the module and then the arguments. These are in the form `.x(y)` where `x` is the identifier in the module definition and `y` is the identifier being passed to the module.

![module instantiation](module_instantiation.png)

Modules can also contain parameters inside the definition or regular text. Parameters are constants local to the specific instance of a module and have default values that can be overridden on instantiation.

![module parameters](module_parameteers.png)

### Gates

The basic gates are inbuilt to verilog: `and`, `or`, `not`, `nand`, `not`, `xor`, `xnor`. These are called using their names, typically in the form:
`and andgate1 (outputwire1, inputwire1, inputwire2);`

Verilog multiplexer example:

![multiplexer verilog example](multiplexer_verilog.png)

### Multibit Signals

Inputs, outputs wires and registers can be multibit. These multibit signals are called vectors, and are defined by specifying a range of bits from MSB to LSB:

![multibit signal](multibit_vector.png)

By setting LSB above 0, the resolution of the signal is reduced, but can allow for a greater max value for the same about of bits. Vectors can also be indexed to select ranges/individual bits from the vector, e.g. `assign y = some[3]` sets `y` to the 4th from LSB bit of `some` and `assign z = some[4:3]` sets `z` to the 5th and 4th from LSB bits of `some`.

Vectors also allow assignments of mismatched vectors - e.g. a 4 bit wire is connected to a 2 bit wire. This does not produce any syntax errors and the left over bits are ignored or set to 0, but can produce logic errors.

### Number Literals

Constant numbers are specified in verilog using the format: \<`size`>'\<`radix`>\<`value`>. `size` is the amount of bits required to store the number in binary and `radix` refers to the numerical system used - `o` for octal, `b` for binary, `h` for hexadecimal, `d` for decimal. e.g.

- 4'b000 = 4 bits storing binary "0000"
- 8'h4F = 8 bits storing hex "4F" = 8 bits storing binary "01001111" = 8'b0100_1111 (underscores can be used for easier reading)
- 4'd11 = 4 bits storing decimal "11" = 4 bits storing binary "1011" = 4'b1011

### Concatenation & Replication

Concatenation is used to string together multiple signals into a single wider signal. This is done using `{}` enclosing a list of signals to be concatenated in the order they appear.

![concatenation](concatentation.png)     `b = a`<sub>`3`</sub>`a`<sub>`2`</sub>`a`<sub>`1`</sub>`a`<sub>`0`</sub>`0000`

Replication is used to copy signals and concatenate them to create wider signals, e.g. `4{a[3]} = a`<sub>`3`</sub>`a`<sub>`3`</sub>`a`<sub>`3`</sub>`a`<sub>`3`</sub>.

## Combinational Verilog

### Assign

**Assign:** The `assign` keyword is a continuous assignment where the result is a combinatorial function of the inputs - no clocks are necessary and it is simpler than using gate modules.

![assign keyword](assign_keyword.png)

This uses inline bitwise operators which are then simplified at compile time to the most efficient use of logic gates/LUTs, as well as allowing for basic arithmetic expressions:

- bitwise
  - `&` - and
  - `|` - or
  - `^` - xor
  - `~` - not
- multibit
  - `+` - addition
  - `-` - subtraction
  - `*` - multiplication
  - `/` - division (can only be used in specific cases, isn't generally synthesizable)

**Conditional Assignments:** The same as a ternary operator in C, where a value is checked and assignment made based on that value.

![conditional assignment](conditional_assignment.png)

All general comparators work and are multibit, e.g. `<`, `>`, `>=`, `<=`, `==`, `!=`.

### Primitives

Verilog allows the creation of primitives, essentially custom logic gates. This is done used a truth table which defines the single output in relation to the inputs. The single output port must be the first port listed in the primitive description.

![primitive verilog](primitive_verilog.png)

### Adders

Simple half adder in Verilog:

![Half adder verilog](half_adder_verilog.png)

Full adder truth table and Verilog implementation using instantiated half adder:

![full adder truth table](full_adder_truthtable.png)

![full adder verilog](full_adder_verilog.png)

Full adder using `assign`:

~[adder using assign](adder_assign.png)

## Behavioural Verilog

Attempts to describe how the circuit behaves as opposed to directly defining the functions required. The implementation tools that interpret the Verilog code design hardware that fulfills the required behaviour.

### `always` block

An `always` block contains procedural or synchronous (not combinatorial) statements that are run when changes occur in specified signals - the sensitivity list. The identifier `*` is used to indicate the block should be rerun if there is a change in any signal used inside the input block.

Regular combinatorial statements, e.g. `assign`, cannot be used inside the always block.

![always block as a circuit component](always_block_as_logic_function.png)

**Registers `reg`:** signals assigned to from within always blocks are declared as `reg` and can be thought of similar to a variable. `reg`s cannot be used with the `assign` statement and also cannot be connected to regular `output` signals of a module - they must be labelled as `output reg`.

Equivalent assign and always blocks:

![equivalent assign and always blocks](equivalent_assign_always.png)

