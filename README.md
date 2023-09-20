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






