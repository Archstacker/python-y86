Python Y86 Utility
========
Copyright (c) 2012 Linus Yang

--------

The Python Y86 utility includes an **assembler** "yas" and a **pipelined simulator** "pipe" for *Y86* (a simplified x86-like ISA described in CMU's *CSAPP*).

The utility is written in Python and **fully compatible** with [Shedskin](https://code.google.com/p/shedskin/wiki/docs), an *RPython to C++ compiler*, which can compile the Python script into binary executables to **improve performance significantly**.

Type "-h" to show help and available options. 

## Y86 Assembler
The Python Y86 assember behaves like the *CSAPP* official **"yas"** assembler, which can generate two kinds of Y86 object file, *ASCII object* and *binary object* in the same folder of ".ys" assembly source.

The **ASCII object** ".yo" file is **fully compatible** with the *CSAPP* official "yis" or "psim" simulator and friendly to read.    
The **binary object** ".ybo" file is generated for the pipelined simulator to execute.

### Features:
- Support **all instructions** of Y86 ISA including "iaddl", "leave" and "cmovXX"
- Support labeling and pseudo instructions, e.g. positioning by ".pos" and code alignment by ".align"
- Large memory address support which can generate **large** size object files
- Fully compatible with **Shedskin**
- Flexible options to specify:
  * Object generation using big-endian or little-endian 
  * Using rules in *CSAPP* 1st editon or 2nd edtion

## Pipelined Y86 Simulator
The Python pipelined Y86 simulator also behaves like the official **"psim"** simulator. But it uses **binary object** ".ybo" generated by "Python Y86 assember" as input.

After execution, the simulator will show brief running results on the screen and generate a log file of each cycle running status. The log syntax is like the official 2nd edtion "psim" simulator output.

### Features:
- Support **all instructions** of Y86 ISA including "iaddl", "leave" and "cmovXX"
- Could deal with all "hazard" conditions mentioned on *CSAPP*
- Logging with detailed running information of every cycle
- Fully compatible with **Shedskin**
- Flexible options to specify:
  * Object generation using big-endian or little-endian 
  * Using rules in *CSAPP* 1st edition or 2nd edition
  * Setting max running cycles to avoid endless loop

## License
This program is distributed under GPLv3.

