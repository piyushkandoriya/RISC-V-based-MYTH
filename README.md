# **RISC-V-based-MYTH**
# Contents 

* [Day 1 -Introduction to RISC-V ISA and GNU compiler toolchain](#Day-1-Introductionto-RISC-V-ISA(instruction-set-architecture)-and-GNU-compiler-toolchain)
    + [Introduction to RISC-V basic Keywords](#Introduction-to-RISC-V-basic-keywords)
      - [introduction](#introduction)
      - [From apps to Hardware](#From-Apps-to-Hardware)
      - [Detailed discription](#Detailed-discription)
      
    + [Labwork for RISC_V software toolchain](#Labwork-for-RISC-V-software-toolchain)
      - [C-Program to compute sum from 1 to N](#C-Program-to-compute-sum-from-1-to-N)
      - [RISC-V GCC compile and Disassemble](#RISC-V-GCC-compile-and-Disassemble)
      - [Spike Simulation and Debug](#Spike-Simulation-and-Debug)
        
    + [Integer number representation](#Integer-number-representation)
      - [64-bit Number system for unsigned Numbers](#64-bit-Number-system-for-unsigned-Numbers)
      - [64-bit Number system for signed Numbers](#64-bit-Number-system-for-signed-Numbers)
      - [Lab for Signed and Unsigned Numbers](#Lab-for-Signed-and-Unsigned-Numbers)
     
 
* [Day 2 -Introductio to ABI and Basic verification flow](#Day-2--Introductio-to-ABI-and-Basic-verification-flow)
    + [Application Binary Interface](#Application-Binary-Interface)
      - [Introduction to Application Binary Interface](#Introduction-to-Application-Binary-Interface)
      - [Memory allocation for Double word](#Memory-allocation-for-Double-word)
      - [Load, Add and Store instructions with example](#Load,-Add-and-Store-instructions-with-example)
      - [Concluding 32-Registers and Their respective ABI names](#Concluding-32--Registers-and-Their-respective-ABI-names)
 
    + [Lab work using ABI function calls](#Lab-work-usin-ABI-function-calls)
      - [Study new algorithm for sum of 1 to N using ASM.](#Study-new-algorithm-for-sum-of-1-to-N-using-ASM.)
      - [Review ASM function call](#Review-ASM-function-call)
      - [Simulate new C program with function call](#Simulate-new-C-program-with-function-call)

    + [Basic verification flow using iverilog](#Basic-verification-flow-using-iverilog)
      - [Lab to run C- program using RISC_V CPU](#Lab-to-run-C--program-using-RISC_V-CPU)
     

* [Day 3 - Digital Logic with TL-verilog and Makerchip](#Day-3---Digital-Logic-with-TL-verilog-and-Makerchip)
    + [Combinational logic in TL-verilog using Makerchip](#Combinational-logic-in-TL-verilog-using-Makerchip)
      - [welcome](#welcome)
      - [Introduction to logic gates](#Introduction-to-logic-gates)
      - [Basic Mux implimentation and introduction to Makerchip](#Basic-Mux-implimentation-and-introduction-to-Makerchip)
      - [Labs for combinational logic](#Labs-for-combinational-logic)
  
 
    + [Sequential logic](#Sequential-logic)
      - [Introduction to sequential logic and Counter lab](#Introduction-to-sequential-logic-and-Counter-lab)
      - [Sequential Calculator lab](#Sequential-Calculator-lab)

    + [Pipelined logic](#Pipelined-logic)
      - [Pipelined logic and Retiming](#Pipelined-logic-and-Retiming)
      - [Pipeline logic advantages and Demo in plateform](#Pipeline-logic-advantages-and-Demo-in-plateform)
      - [Lab on error conditions within computation pipeline](#Lab-on-error-conditions-within-computation-pipeline)
      - [Lab on 2-Cycle Calculator](#Lab-on-2--Cycle-Calculator)

    + [Validity](#Validity)
      - [Introduction to Validity and it's advantages](#Introduction-to-Validity-and-it's-advantages)
      - [Lab on Validity and valid when condition](#Lab-on-Validity-and-valid-when-condition)
      - [Lab to commpute total distance](#Lab-to-commpute-total-distance)
      - [Lab on 2-Cycle Calculator with validity](#Lab-on-2--Cycle-Calculator)
      - [Calculator Singal value Memory lab](#Calculator-Singal-value-Memory-lab)

    + [Wrap up](#Wrap-up)
      - [Introduction to Hierarchy concept](#Introduction-to-Hierarchy-concept)
      - [Day_3 closer](#Day_3-closer)

  * [Day 4 -Basic RISC-V CPU Micro-architecture](#Day-4--Basic-RISC-V-CPU-Micro-architecture)
    + [Introduction to simple RISC-V Micro-architecture](#Introduction-to-simple-RISC-V-Micro-architecture)
      - [Micro-architecture of single cycle RISC-V CPU](#Micro-architecture-of-single-cycle-RISC-V-CPU)
      - [Starting point code for RISC-V labs part-1](#Starting-point-code-for-RISC-V-labs-part-1)
      - [Starting point code for RISC-V labs part-2](#Starting-point-code-for-RISC-V-labs-part-2)
      
    + [Fetch and decode](#Fetch-and-Decode)
      - [Implementation plan and lab for PC](#Implementation-plan-and-lab-for-PC)
      - [Labs for intruction Fetch logic](#Labs-for-intruction-Fetch-logic)
      - [Lab for RV instruction Types IRSBJU decode logic](#Lab-for-RV-instruction-Types-IRSBJU-decode-logic)
      - [Lab for instruction immediate decode logic for RV-ISBUJ](#Lab-for-instruction-immediate-decode-logic-for-RV-ISBUJ)
      - [Labs to decode other fields of instruction for RV-ISBUJ](#Labs-to-decode-other-fields-of-instruction-for-RV-ISBUJ)
      - [Labs to decode instruction field based on Instr type RV-ISBUJ](#Labs-to-decode-instruction-field-based-on-Instr-type-RV-ISBUJ)
      - [Labs to decode individual instruction](#Labs-to-decode-individual-instruction)
        
    + [RISC-V control logic](#RISC-V-control-logic)
      - [Lab for register file read part-1(USE UPDATED SHELL CODE)](#Lab-for-register-file-read-part-1(USE-UPDATED-SHELL-CODE))
      - [Lab for register file read part-2](#Lab-for-register-file-read-part-2)
      - [Lab for ALU operations for add/addi](#Lab-for-ALU-operations-for-add/addi)
      - [Lab for register file write](#Lab-for-register-file-write)
      - [Concept of Array and Register file details](#Concept-of-Array-and-Register-file-details)
      - [Labs for Implementing branch instructions](#Labs-for-Implementin-branch-instructions)
      - [Labs for complementing branch instructions implementaion](#Labs-for-complementing-branch-instructions-implementaion)
      - [Lab to create simple Testbench](#Lab-to-create-simple-Testbench)

   * [Day 5 -Complete pipelined RISC-V CPU micro-architecture](#Day-5--Complete-pipelined-RISC-V-CPU-micro-architecture)
    + [Pipelining the CPU](#Pipelining-the-CPU)
      - [Introduction to Control flow Hazard and Read after write Hazard](#Introduction-to-Control-flow-Hazard-and-Read-after-write-Hazard)
      - [Lab to create 3-Cycle valid signal](#Lab-to-create-3-Cycle-valid-signal)
      - [Lab to code 3-Cycle RISC-V to take care of invalid Cycles](#Lab-to-code-3-Cycle-RISC-V-to-take-care-of-invalid-Cycles)
      - [Lab to modify 3-Cycle RISC-V to distribute logic](#Lab-to-modify-3-Cycle-RISC-V-to-distribute-logic)
      
    + [Solution to pipeline Hazards](#Solution-to-pipeline-Hazards)
      - [Lab for register file bypass to address Rd-After-Wr Hazard](#Lab-for-register-file-bypass-to-address-Rd-After-Wr-Hazard)
      - [Lab for branches to correct the branch target path](#Lab-for-branches-to-correct-the-branch-target-path)
      - [Lab to complete instruction decode except Fence,Ecell,Ebreak](#Lab-to-complete-instruction-decode-except-Fence,Ecell,Ebreak)
      - [Lab to code complete ALU](#La-to-code-complete-ALU)
        
    + [Load/Store Instructions and completing RISC-V CPU](#Load/Store-Instructions-and-completing-RISC-V-CPU)
      - [Intriduction to load/store instruction and lab to Redirect loads](#Intriduction-to-load/store-instruction-and-lab-to-Redirect-loads)
      - [Lab to load data from memory to register file](#Lab-to-load-data-from-memory-to-register-file)
      - [Lab to instantiate data memory to register file](#Lab-to-instantiate-data-memory-to-register-file)
      - [Lab for add, stores and load to the test program](#Lab-for-add,-stores-and-load-to-the-test-program)
      - [Lab to add control logic for jump instruction](#Lab-to-add-control-logic-for-jump-instruction)
      - [Wrap up](#Wrap up)
    
 * [References](#References)
   
 * [Acknowledgement](#Acknowledgement)
    

# Day 1 -Introduction to RISC-V ISA(instruction set architecture) and GNU compiler toolchain	 
## Introduction to RISC-V basic keywords
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

### From Apps to Hardware
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

## Labwork for RISC V software toolchain
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
what we get at output by using compiler gcc, same thing we will get by using this "riscv-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o Sum1toN.o Sum1toN.c" compiler.
For seeing output here, command is "spike pk Sum1toN.o".

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

## Integer Number representation
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
Let's write simple program for Highest unsigned integer in C.let's create file UnsignedHighest.c using command "leafpad UnsignedHighest.c &".

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/d8bfcf1a-a939-434b-b27c-de1ed03daab1">

Here, we can not use normal "unsigned int" to declare Max. To declare double word we have to use "unsigned long long int".
Now after run this program by command "gcc UnsignedHighest.c". Now if we open the output file by command "./a.out", we can see the maximum unsigned number represent by double word is =18,446,744,073,709,551,615

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/aa669cc3-cc2b-476c-b2f9-526b64aeaefb">

This is the highest number represent by "doubleword" or "unsined long long int". To check it, if we change in the code "64" to 66 then also we get the same value 18,446,744,073,709,551,615 because doubleword can not contain more than this value.

If we try to represend nagative number by "unsigned long long int" then it will show "0" because it will goes only up to 0. for that let's change "(pow(2,64)-1)" to "((pow(2,64)-1)*-1). 

<img width="959" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ce1f3f8c-fe7a-40d4-8d14-4f54a23537fa">

we can see the result is 0. Hence it proven that we can not represent nagative number by "unsinged long long int".

Now how to represent nagative number. For that Let's write simple program for Highest signed integer in C. let's create file signedHighest.c using command "leafpad signedHighest.c &".

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/7e0461f9-cd9e-4802-9e78-1b7b07917d23">

Here, we can not use normal "int" to declare Max. To declare doubleword we have to use "long long int". and we have to use formate spacifier "%lld" instead of "%llu".
Now after run this program by command "riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o SignedHighest.o SignedHighest.c". Now if we open the output file by command "spike pk SignedHighest.o", we can see the maximum unsigned number represent by doubleword is =9223372036854775807

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/4cd1f19b-5dd1-46e2-8c6d-8f38730587cc">

Now to find lowest number, we have to change (pow(2,63)-1) to (pow(2,63)*-1).

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/e82d0d8a-b63e-4102-9996-e2ecda789ea2">

Here we can see the negative highest number represent by doubleword is= -9223372036854775807

# Day 2 -Introductio to ABI and Basic verification flow	 
## Application Binary Interface
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

## Lab work using ABI function calls
### Study new algorithm for sum of 1 to N using ASM.
Let's take an example of Sum 1 to N,

<img width="288" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/5920ae39-74f7-47c9-bd92-341a872d5b4f">

Here arguments passed using Registers a0 and a1 and get back return using a0.
Algorithm of this program will looks like this given below,

<img width="354" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/4d3698de-4688-4937-a6a2-db8230274d06">

### Review ASM function call
Till now we have algorithm. now let's look into the real main c-program and assembly language program for this algorrithm.

<img width="772" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f2ff61f9-b68a-4ed3-8d2d-235404473bf3">

Here, "extern" keyword informs the compiler that the function "load" is declared in this ISA. It's a way of indicating that the actual function implementation exists externally.
By using load we will pass (0x0, count+1) number to assambly language program. Then it will goes into function and return into the result.

Now let's creat "load.S" file like this.

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/abb74298-0dc5-4aa5-866f-46984f42777d">

Here we declare this function "load". 

If we see in the algorithm, c program pass the value of 0 and 10 by register a0 and a1. These values of a0 and a1 are now move to a4 and a2 register. And initialize the a3 register with 0. These process we write into assambly language by command "add a4, a0, zero", "add a2, a0, a1" , "add a3, a0, zero". 

Now as per the loop also we write a program. like these we define the "load" function in "load.S" file.


### Simulate new C program with function call
Let's we run the 1to9_custom.c program by command "riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o 1to9_custom.o 1to9_custom.c load.S".

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/465e3c2b-0f05-4b44-a41a-12832ec1bc80">

Here we can see the output is 45. 

So, conclusion is we can run the program in RISC_V also by just passing the value of interger by C-language. This is done by ABI(application binary interface) or (assembly function call).


## Basic verification flow using iverilog
### Lab to run C- program using RISC_V CPU
Till now we run the direct C-program, we run C-program with ASM function call. But these are the simulations only.
Now we will see, how we can run the same C-program on RISC_V CPU.

<img width="403" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/7807eef8-61b2-411c-8c1c-60a984756b19">

As we can see here, first we will convert our C program into Hex formate and the we will store it into memory. Then we will load this memory containt into RISC_V CPU (which is written in verilog). Then we run the testbench according to our input and then we display the output of these RISC_V CPU.

Now in lab first we download some basic labs by "git clone". Command for this is "git clone https://github.com/kunalg123/riscv_workshop_collaterals.git".

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/454e9b47-0c4f-45fe-b08d-636d540e919a">

Now we can see the bunch of files in the "riscv_workshop_collaterals" file. 

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/d1a28c51-8b66-4dca-80c5-1d221aa4c45d">

We will goes into the "labs" file. In this file we can see one of the RISC_V CPU "picorv32.v".(as we mention, CPU is written in verilog. so extention is ".v"). 

<img width="953" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/409c9bd9-cd4c-4e88-9f89-4bb3e54b8d80">

Now if we open this CPU (picorv32.v) by command "vim picorv32.v", we can see the verilog file of this CPU.

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/89ce93b3-ee84-4b5c-8c6a-620ef5709918">

Now let's see the testbench for this verilog code by command "vim testbench.v".

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/70494b1f-e248-4984-b356-55b135d0baa9">

Here by this testbench, we load our hex file of C-program (which is available into memory) into CPU.

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b4dec654-ccb0-4b9d-8dc6-c92f0263e203">

Now let's see the script or command, which are required to convert c-program into hex file. for that open the "rv32im.sh" by command "vim rv32im.sh".

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/e41b56c4-7252-4c2a-802c-26cfb2cf8ce5">

Here we can see the many commands which will convert these C file and Assembly language file into hex file. So at the end we get ".hex" file.
Then we use the tool "iverilog" and input of this tool is "testbench.v" and "picorv32.v". and this tool will generate "testbench.vvp" file. 
And finally we will simulate the activity contain by "testbench.vvp" file by command "vvp -N testbench.vvp".

Now let's run these command to generate ".hex" file by using the command "chmod 777 rv32im.sh" and press "enter" and again type command "./rv32im.sh". now whole command will run.

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/bdc060ce-9c1b-4887-987d-5c50efc7ed0c">

here, Our Cprograme and assably code is for only 1 to 2, so we get sum = 3 here.

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/139e0b51-17fa-415a-97a5-acee0124bb4e">


Now lets change the c program for bigger number i.e., 3. by command "vim 1to9_custom.c". (to edit this vim file: after open the vim file, we have to press i for start the insert mode end then we have to press "Esc,:,w" to save the changes and then we can exit from vim file by "Esc,:,q").

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ecff2ad2-6c85-4a4f-9dd9-0ef8735c698a">


Now if we run once again by commands "chmod 777 rv32im.sh" and press "enter" and again type command "./rv32im.sh". 

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/59b0e5f7-75ee-4dda-a72f-6cad28daaeb3">

we can see the output is 6.

After running these script or commands for creat the ".hex" file. we can see this hex file now.

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/2a3d5508-83ac-4174-86b7-7bdecd406ea2">

let's open this hex file by command "vim firmware32.hex"

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/31b8d369-5b9a-4954-8150-25cf41beabeb">

As we said, this will used by picorv32 module of cpu. to see that, open the testbench by "vim testbench.v"

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/eabfc7c2-8b5b-4acc-822a-61f1db4dc4eb">

Now we will build the RISC_V CPU in transister level verilog from srecth in Day_3, Day_4 and Day_5.



# Day 3 - Digital Logic with TL-verilog and Makerchip
## Combinational logic in TL-verilog using Makerchip
### welcome



