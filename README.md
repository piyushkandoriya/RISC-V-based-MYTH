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




