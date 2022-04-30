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

