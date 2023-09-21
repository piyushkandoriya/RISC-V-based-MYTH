# **RISC-V-based-MYTH**
# Contents 
 <div class="toc">
  <ul>
    <li><a href="#header-1">Day 1 - Introduction to RISC-V ISA and GNU compiler toolchain </a></li>
	<ul>
        <li><a href="#header-1_1">Introduction to RISC-V basic keyword</a></li>
      </ul>
      <ul>
        <li><a href="#header-1_2">Labwork for RISC_V software toolchain</a></li>
      </ul>
	<ul>
        <li><a href="#header-1_3">Integer number representation</a></li>
      </ul>
   </div>
     
<div class="toc">
  <ul>
    <li><a href="#header-2">Day 2 - Introduction to ABI and basic verification flow</a></li>
	<ul>
        <li><a href="#header-2_1">Application Binary interface (ABI)</a></li>
      </ul>
      <ul>
        <li><a href="#header-2_2">Labwork using ABI function calls</a></li>
      </ul>
	<ul>
        <li><a href="#header-2_3">Basic verification flow using iverilog</a></li>
      </ul>
</div>
  
  <div class="toc">
  <ul>
    <li><a href="#header-3">Day 3 - Digital Logic with TL-verilog and Makerchip</a></li>
	<ul>
        <li><a href="#header-3_1">Combinational logic in TL-verilog using Makerchip</a></li>
      </ul>
      <ul>
        <li><a href="#header-3_2">Sequential Logic</a></li>
      </ul>
	<ul>
        <li><a href="#header-3_3">Pipelined logic</a></li>
           </ul>
	<ul>
	<li><a href="#header-3_4">Validity</a></li>
	</ul>
	  <ul>
		  <li><a href="#header-3_5">Warm-up</a></li>
	  </ul>
   </div>
	  
<div class="toc">
  <ul>
    <li><a href="#header-4">Day 4 -Basic RISC-V CPU Micro-architecture</a></li>
	<ul>
        <li><a href="#header-4_1">Introduction to simple RISC-V Micro-architecture</a></li>
      </ul>
      <ul>
        <li><a href="#header-4_2">Fetch and decode</a></li>
      </ul>
	<ul>
        <li><a href="#header-4_3">RISC-V control logic</a></li>
      </ul>
</div>
	
<div class="toc">
  <ul>
    <li><a href="#header-5">Day 5 -Complete pipelined RISC-V CPU micro-architecture</a></li>
	<ul>
        <li><a href="#header-5_1">Pipelining the CPU</a></li>
      </ul>
      <ul>
        <li><a href="#header-5_2">Solution to pipeline Hazards</a></li>
      </ul>
	<ul>
        <li><a href="#header-5_3">Load/Store Instructions and completing RISC-V CPU</a></li>
        </ul>
</div>
	
<div class="toc">
  <ul>
    <li><a href="#header-6">References</a></li>
  </ul>
</div>

<div class="toc">
  <ul>
    <li><a href="#header-7">Acknowledgement</a></li>
  </ul>
</div>

# <h1 id="header-1">Day 1 -Introduction to RISC-V ISA(instruction set architecture) and GNU compiler toolchain</h1>	 
## <h1 id="header-1_1">Introduction to RISC-V basic keyword</h1>
### Introduction
ISA (Instruction Set Architecture) is nothing but language of the computer in which we are giving some command to the computer.

For example if we have a C-program like this,

<img width="72" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b6ad9f86-fa2f-4e86-8483-18902b60e7b1">

And we want to run this program in a hardware of our computer like this,

<img width="281" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/254ce94f-487b-4edb-908d-2f563ed8c2e9">

This is nothing but the layout of our computer hardware.
To run this program, first this program will compile in assembly language (which is nothing but RISC-V assembly language program for above code) 

<img width="69" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/5318e198-6721-47f4-8f4d-2c8b30c73c11">

Then this assembly language program will converted into machine language program (which is nothing but binary language program).

<img width="69" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f6abdac5-4683-4d23-8b0e-2ad08adad02e">

Then this binary program will executed in layout. Now layout will give output.
Another interface that can be required between RISC-V and layout is Hardware discription language interface. we need to create RISC-V specifications using some RTL like this Picorv32 module,

<img width="404" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/23e462a6-6561-4293-a552-5f40e8b25452">

So, complete flow is like RISC-V architecture --> Implementation using HDL --> Layout

### From App to Hardware
#### How Apps run on Hardware?
By example of Stop watch App, we understand this.

<img width="251" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/fe3e5b2f-76ed-4fb3-a030-6b25fa40f109">

The output of this stopwatch from the os is simple C-program like this,

<img width="273" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f7e210c9-c06b-4d55-9bee-caaede40d90b">

This program is input of compiler and compiler converted this C-Program into assembly language program. This compiler is depends on the type of hardware. means it will generate instructions in assambly language which that perticular hardware (i.e, RISC-V, MIPS, intel 8086 etc.).

<img width="140" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/81e2d33a-d0cc-4659-b3d4-52a6213a6c6c">

That perticular assably language instruction set will be the input for assambler and it will converted into machine language (binary language) which can hardware understand.

<img width="152" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/4027cee5-dbd9-4580-818c-4047cbf203b4">

So the entire flow is like given below,

<img width="560" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/1a17d58b-4686-4d16-b8bf-a1e9422beeba">

we will more focus on the instruction sets of RISC-V architecture here.

In betweet RISC-V architecture and hardware, we have to implement this instruction set into RTL and it will be synthesis and generate on netlist which contains gate, flip-flops, etc. and then we done Physical design of this netlist to made hardware.

### Detailed discription 
Let's take an example of basic addition, multiplication and divisionn of calculator which is available in our computer app.
Here, shown is C-program code for above mentioned operations,

<img width="625" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/5c9a85da-fcc0-40bb-b3d5-a58de6cf1f70">

It will given to compiler and compiler will generate assembly language instruction set based on RISC-V architecture then assembler will converted into Binary or haxadecimal code like given below,
For addition,

<img width="185" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/4170303a-89f9-4dd8-95d3-caf4c7b013e9">

For multiplication and division,

<img width="181" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/43de01a1-31eb-439e-ae43-098f3640ccf4">

Here, we can see the in instrucions, mv (move), li (Load imidiate), ret (return). These instructions are catagerized as "pseudo insructions".

<img width="538" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/bf54d7c3-66cc-4847-be4b-cac06a8b11e0">

Other instructions like addi, sd, jalr, lui etc are catagerizes as "base integer instructions".

<img width="532" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/5da06270-ac43-46a8-8ea9-4baf0fabb3f5">

Other than these, there are two other instructions are available in code are, mulw ,divw, etc . These are catagerized as "multiply extension".

<img width="532" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ef755719-0c31-46ad-b86d-98f266194f1a">

Similarly for floating point addition and floating point multiplication and division, C-program is given below,

<img width="173" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/4897c04a-526f-4308-a64b-46cea8bf8159">
<img width="223" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/e0848fa5-6183-46e6-b1a0-6bed0150adf6">

And if we see the assembly language programe of these codes, we can see some new instructions like flw,fmv,etc. These are catagerized into "single and double precision floating point extention".

<img width="223" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/3f9fc4e6-eb28-4be1-8c58-d6f91b22ab8e">

Other than these instructions, there are some keywords are available in assembly code, these are interface by we can access the registers of RISC-V by this interface directly. These interface is called application binary interface (ABI).

<img width="535" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/57333355-e014-4b9d-a890-9d177816cd94">

By some instructions, some memory transfer heppend. so these instructions are categerized as "memory allocation and stack pointer".

<img width="533" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/2eedbbcb-94cc-4f78-a69e-8cba1676a027">

## <h1 id="header-1_2">Labwork for RISC_V software toolchain</h1>
### C-Program to compute sum from 1 to N
C-program for sum of 1 to N is,

<img width="959" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f8a924a4-2c57-45a5-a69a-c8a11741f300">

Here we use "gcc" for compile the program. GCC tends for GNU Compiler Collection.
After compiling ww got output for N=5, N=100, N=10, N=50 and N=3.

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b78810ad-5bfa-4c56-ae09-728b3f0d8a4d">

### RISC-V GCC compile and Disassemble
#### Note:
we use "cat" command to reads data from the file and gives its content as output. "cat" tends for concatenate.
we open the program.
Now, we will compile this program with different RISC-V GCC compiler by command "riscv-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o Sum1toN.o Sum1toN.c".
Here we can this Sum1toN.o file.
<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/41f129a3-ff9a-4eb3-856c-c984db791099">

Now we will see the Assembly code for this C-program in another terminal, by command "riscv-unknown-elf-objdump -d Sum1toN.o".
Here we can see the instruction set for the C-program in assembly language,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/99587625-bf28-4cf3-a851-e3839fcb75a8">

Now by searching "main" section we get instructions and address of "main" section.

<img width="959" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/47e972a4-bb1f-4d19-937d-c32fb92ddcb8">

Adress of "main" is 10184 and other instructions were given below ara at 10188,10192 etc. so memory is byte addressable (4 byte for 1 instruction. so instruction is 32bit instruction). Total 26 instruction came out of "O1" compiler.

Lets run same program in the other compiler -Ofast instead of -O1 by command "riscv-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o Sum1toN.o Sum1toN.c".

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ff660bed-1bb7-44b5-87aa-573cc0d48037">
<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/a70dc315-ae25-4c7d-b5bd-70f3d7900bbf">

Now here, Adress of "main" is 100b0 and other instructions were given below ara at 100b4,100b8 etc. so here also memory is byte addressable (4 byte for 1 instruction. so instruction is 32bit instruction). Total 26 instruction came out of "Ofast" compiler.

### Spike Simulation and Debug
what we get at output by using compiler gcc, same thing we will get by using this "riscv-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o Sum1toN.o Sum1toN.c" compiler
For that command is "spike pk Sum1toN.o".

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f718810e-18dc-4267-bac4-b8646e69d530">

Here also we get sum=15 for N=5 and sum=5050 for N=100. means our simulation is correct.
Now let's debug the instructions by the command "spike -d pk Sum1toN.o".
Now first we run all the instruction up to "main" and move our program counter at the address of 100b0 by command "untill pc 0 100b0"

Now before executing next instruction let's find the value in register "a0" by command "reg 0 a0"

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/7ef8235a-3cba-457e-9b7b-c72edc19fc4a">


Here we can clearly see that, upto now value of register a0=1.

Now executing the next instruction by just pressing enter". and again check the value of register a0 now.

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f930246c-b5f8-4803-b934-33554c0e5573">

Now the value of Register a0 is 2b000.
Here instruction "lui" means load upper immediate. so here also immediate bit 64-12 are filled with 0b which is followed by "lui ao 0×2b".

Now again when we press enter, next instruction will exicuted which is "addi sp, sp, -32". this instruction means stack pointer will updated by sp=sp-32.
So before exicuting this let's see the value of Stack pointer (sp) first. Sp have value of "3ffffffb50".then we check the change in sp.

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/15391d9d-9585-45a0-87e9-a8fdce0476e0">

Now sp have value of "3ffffffb50". Here we can see that SP is reduced by 32 because (20)h=(32)10.

## <h1 id="header-1_3">Integer Number representation</h1>
### 64-bit Number system for unsigned Numbers
we need to understand, what kind of conversion happened when we convert any number from a decimal format to a binary format and how does the things are getting arranged and implemented by RISC-V implementation.
So binary representation of signed of unsigned integer is relevantly very immportant.
In the turms of RISC-V, entire 64 bit is called "doubleword". and 32-bit is called word.
In the turms of RISC-V, 8-bit= 1 byte, 4-byte=1 word, 2-word=doubleword

<img width="594" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/c17c69ec-f07f-4fd1-bacb-83132f017e40">

Total number of pattern represented by RV64 is:2^64.
Range of unsigned interger number in RV64 is: 0 to [(2^64)-1].
The maximum sum of any unsigned number or maximum possible nnumber respresented in RV64 is :[1111111......1(64times)]binary = (18,446,744,073,709,551,615)decimal.

<img width="527" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f4c69337-94e1-49b6-ae36-06bf06c984c1">

After this decimal number, the overflow flag generate.

### 64-bit Number system for signed Numbers
Till now we see about positive Numbers. 
How to represent the nagative numbers?
To represent nagative number, we have to use 2's complement of positive number.
In signed representation, MSB represent the sign of Number. i.e, if MSB=0 then Number is Positive. 

<img width="517" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/0e9dd5cd-8d7d-4bf7-a663-b1ca37e1652e">

if MSB=1 then Number is Nagative. So we have to convert in to 2's complement to get origional number.

<img width="514" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/74edb62e-7800-4cb9-96ee-d36bc4195520">

For more understandin, let's take an example of (+2) and (-2).

<img width="517" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b4d2fc75-9000-45eb-9a92-9669caf8ce50">
ca
The rang that can be represented as signed number by RV64 is: -(2^63) to [(2^63)-1].

### Lab for Signed and Unsigned Numbers




# <h2 id="header-2">Day 2 -Introductio to ABI and Basic verification flow</h2>	 
## <h2 id="header-2_1">Application Binary Interface</h2>
### Introduction to Application Binary Interface
For computers, the interface for the users is the just appearence and functionality.

<img width="449" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/c9764b7a-6910-4b4b-8c33-2f93f604fcda">

Similar way if we looking at any application like Email, if we want to run the program of email application in Hardware, there are multiple layers which are present at each and every stage of program. from that layers, One of the layer is ABI (application binary interface).

When we write the program, we use some standerd libraries. so, between lybraries and application program, there is an interface is available. which is called API (application programing interface). similarly other interfaces also available like ISA, RTL etc. ISA is accesable to O.S. and User directly. so some part of ISA called "User ISA" and "User and System ISA".

<img width="529" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/3b1c2c16-4524-474e-83a0-6a8e39cb1066">

User directly access the registers vai system calls. By using the interface, user access registers via system calles is called ABI (application binary interface). It is also called "system call interface".

<img width="515" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/987c12dd-bd8d-415f-b2f1-e3dbab27be59">

In RISC-V, there are 32 registers are available.

### Memory allocation for Double word
#### Why only 32 registers in RISC-V architecture?
Two ways to load the data in registers. (i) Direct loading in register (ii) Taking data from memory and the loading to register

<img width="536" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/dd264b08-245b-4cb2-8b32-53aa7573f594">

If the address of first doubleword is M[0] then adderess of second doubleword is M[8] and adress of third doubleword is M[16]

<img width="529" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/27e33499-d447-4f0b-a9e5-9c6a16c54e4a">

### Load, Add and Store instructions with example
Let's take an example of array which holds 3 doublewords. means it will strord from 0-7,8-15,16-23 memory locations.

<img width="526" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/a8c6f846-9907-490f-8bad-5d066410197f">

What we need is, we need to store this content of array's 3rd doubleword (16-23) in register (X8).
For that first we need to store the location of first memory address where first byte of first word is stored. so lets take register "x23" contains the adreess of first memory location.

Now to load the data of 3rd doubleword, we have to give command "ld x3, 16(X23)". where ld= load doubleword, 16(x23) means stake pointer will move to adress of (x23 address + 16).

<img width="539" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/cf8315c2-083e-4d32-8c8e-5e3badb1407c">

Let's see how it instructions looks like,

<img width="452" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/636c6198-69bc-4100-a6c6-a1423c3e392f">

#### NOte
Data in RISC-V is 64 bit in size but instruction size is 32 bit.

Other instruction is "add x8,x24,x8" means we add the value of register x23 into x8. let's see how it is looks like,

<img width="427" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/d20c7925-10ae-4e87-9637-326ac0484198">

Other instruction is "sd x8,8(x23)". Here sd means store doubleword. here we are are storing the value of x8 register frpm memory M[8] to M[15] because 8(x23) means memory address contain by x23 + 8= M[8]. let's see how it is looks like,

<img width="454" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/88317401-29ee-4076-bd20-0e1c8b085364">

### Concluding 32-Registers and Their respective ABI names 
ld,add,sd are base integer istructions in RV64I. under these, add is called R-type instruction because it is implemented on register only. similarly, ld is called i-type instrtuction where imedeate bits are use for perform the operaration and sd is called S-type instruction here sourse register is used.

<img width="467" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/17b2b3b1-9fd5-411f-b9b3-5be252567499">

All the registers address in intructions is only 5 bit. so total 32 registers we required in RISC-V aarchitecture.

<img width="528" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/a50c96e5-5ae2-4ab2-b825-3d94d353004c">

In assembly language, we use these ABI name to call these registers.

<img width="530" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/d4eac350-0914-4b87-acab-dab89b97c691">

## <h2 id="header-2_2">Lab work using ABI function calls</h2>
### Study new algorithm for sum of 1 to N using ASM.
