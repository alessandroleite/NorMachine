The NOR Machine

![logo] (http://pragprog.com/magazines/2012-03/images/iStock_000015471891Small.jpg)

The [NOR Machine][normachine] is a CPU with Only One Instruction written by Alexander Demin and published in [PragPub][pragpub] magazine.

## CPU’s Architecture

So NOR gives us everything we need to compute anything in bits. All right, we have established our single function. Now let’s sketch out an overall architecture for our CPU.

We will have a linear memory organization containing 2^16 (65536 or 0xFFFF), cells, and consequently a range of valid addresses from 0 (0x0000) to 65535 (0xFFFF), 16 bits per address. So far this CPU is similar to classical microprocessors like the Intel 8080 or Zilog Z80. But from here on it’s going to get really different.

The first significant difference is that memory cells in our CPU will be 16-bit, not 8-bit, so one cell can hold a range of values from 0x0000 to 0xFFFF.

The next difference is more important. Normally, in both RISC and CISC architectures of modern CPUs, each individual instruction consists of two parts: an operation code, or opcode, and some number of arguments. The opcode specifies an operation to perform and the arguments define the details of a particular instruction.

But remember, our CPU understands only one instruction. So we don’t need the opcode, because we always compute NOR! Our instructions will only contain the arguments—the arguments of NOR.

Now we have to settle on a binary format for our instructions. Each instruction will reside in three consecutive cells in the memory. The first and second cells will contain addresses of the NOR arguments, a and b respectively. The third argument will contain the address where the result of the NOR will be placed.

[pragpub]: http://pragprog.com/magazines/
[normachine]: http://pragprog.com/magazines/2012-03/the-nor-machine
