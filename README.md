# **RISC-V-based-MYTH**
# Contents 

* [Day 1 -Introduction to RISC_V ISA and GNU compiler toolchain](#Day-1--Introduction-to-RISC_V-ISA-and-GNU-compiler-toolchain)
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
      - [Load Add and Store instructions with example](#Load-Add-and-Store-instructions-with-example)
      - [Concluding 32_Registers and Their respective ABI names](#Concluding-32_Registers-and-Their-respective-ABI-names)
 
    + [Lab work using ABI function calls](#Lab-work-using-ABI-function-calls)
      - [Study new algorithm for sum of 1 to N using ASM](#Study-new-algorithm-for-sum-of-1-to-N-using-ASM)
      - [Review ASM function call](#Review-ASM-function-call)
      - [Simulate new C program with function call](#Simulate-new-C-program-with-function-call)

    + [Basic verification flow using iverilog](#Basic-verification-flow-using-iverilog)
      - [Lab to run C- program using RISC_V CPU](#Lab-to-run-C--program-using-RISC_V-CPU)
     

* [Day 3 -Digital Logic with TL verilog and Makerchip](#Day-3--Digital-Logic-with-TL-verilog-and-Makerchip)
    + [Combinational logic in TL verilog using Makerchip](#Combinational-logic-in-TL-verilog-using-Makerchip)
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
      - [Lab on 2-Cycle Calculator](#Lab-on-2-Cycle-Calculator)

    + [Validity](#Validity)
      - [Introduction to Validity and its advantages](#Introduction-to-Validity-and-its-advantages)
      - [Lab on Validity and valid when condition](#Lab-on-Validity-and-valid-when-condition)
      - [Lab to commpute total distance](#Lab-to-commpute-total-distance)
      - [Lab on 2-Cycle Calculator with validity](#Lab-on-2-Cycle-Calculator)
      - [Calculator Singal value Memory lab](#Calculator-Singal-value-Memory-lab)

    + [Wrap up](#Wrap-up)

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
      - [Labs of complete instruction decode](#Labs-of-complete-instruction-decode)
        
    + [RISC-V control logic](#RISC-V-control-logic)
      - [Lab for register file read part-1](#Lab-for-register-file-read-part-1)
      - [Lab for register file read part-2](#Lab-for-register-file-read-part-2)
      - [Lab for ALU operations for add/addi](#Lab-for-ALU-operations-for-add/addi)
      - [Lab for register file write](#Lab-for-register-file-write)
      - [Concept of Array and Register file details](#Concept-of-Array-and-Register-file-details)
      - [Labs for Implementing branch instructions](#Labs-for-Implementin-branch-instructions)
      - [Labs for complementing branch instructions implementaion](#Labs-for-complementing-branch-instructions-implementaion)
      - [Full RISC-V architecture with testbench](#Full-RISC-V-architecture-with-testbench)
      

* [Day 5 -Complete pipelined RISC-V CPU micro-architecture](#Day-5-Complete-pipelined-RISC-V-CPU-micro-architecture)
    + [Pipelining the CPU](#Pipelining-the-CPU)
      - [Introduction to Control flow Hazard and Read after write Hazard](#Introduction-to-Control-flow-Hazard-and-Read-after-write-Hazard)
      - [Lab to create 3-Cycle valid signal](#Lab-to-create-3-Cycle-valid-signal)
      - [Lab to code 3-Cycle RISC-V to take care of invalid Cycles](#Lab-to-code-3-Cycle-RISC-V-to-take-care-of-invalid-Cycles)
      - [Lab to modify 3-Cycle RISC-V to distribute logic](#Lab-to-modify-3-Cycle-RISC-V-to-distribute-logic)
      
    + [Solution to pipeline Hazards](#Solution-to-pipeline-Hazards)
      - [Lab for register file bypass to address Rd-After-Wr Hazard](#Lab-for-register-file-bypass-to-address-Rd-After-Wr-Hazard)
      - [Lab for branches to correct the branch target path](#Lab-for-branches-to-correct-the-branch-target-path)
      - [Lab to complete instruction decode except Fence and Ecell and Ebreak](#Lab-to-complete-instruction-decode-except-Fence-and-Ecell-and-Ebreak)
      - [Lab to code complete ALU](#Lab-to-code-complete-ALU)
        
    + [Load and Store Instructions and completing RISC-V CPU](#Load-and-Store-Instructions-and-completing-RISC-V-CPU)
      - [Intriduction to load and store instruction and lab to Redirect loads](#Intriduction-to-load-and-store-instruction-and-lab-to-Redirect-loads)
      - [Lab to load data from memory to register file](#Lab-to-load-data-from-memory-to-register-file)
      - [Lab to instantiate data memory to register file](#Lab-to-instantiate-data-memory-to-register-file)
      - [Lab for add and stores and load to the test program](#Lab-for-add-and-stores-and-load-to-the-test-program)
      - [Lab to add control logic for jump instruction](#Lab-to-add-control-logic-for-jump-instruction)
      - [Final 4 stage RISC-V pipelined architecture](#Final-4-stage-RISC-V-pipelined-architecture)
      - [Wrap up](#Wrap-up)
    
 * [References](#References)
   
 * [Acknowledgement](#Acknowledgement)

 * [Inquiries](#Inquiries)
    

# Day 1 -Introduction to RISC_V ISA and GNU compiler toolchain	 
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

### Load Add and Store instructions with example
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

### Concluding 32_Registers and Their respective ABI names 
ld,add,sd are base integer istructions in RV64I. under these, add is called R-type instruction because it is implemented on register only. similarly, ld is called i-type instrtuction where imedeate bits are use for perform the operaration and sd is called S-type instruction here sourse register is used.

<img width="467" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/17b2b3b1-9fd5-411f-b9b3-5be252567499">

All the registers address in intructions is only 5 bit. so total 32 registers we required in RISC-V aarchitecture.

<img width="528" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/a50c96e5-5ae2-4ab2-b825-3d94d353004c">

In assembly language, we use these ABI name to call these registers.

<img width="530" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/d4eac350-0914-4b87-acab-dab89b97c691">

## Lab work using ABI function calls
### Study new algorithm for sum of 1 to N using ASM
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



# Day 3 -Digital Logic with TL verilog and Makerchip
## Combinational logic in TL verilog using Makerchip
### Introduction to logic gates
Truth table and boolean function of different logic gates

<img width="511" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/500e9934-cf23-48a8-a209-2344c08c134f">

Combinational circuit for 3-bit full adder 

<img width="496" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/5ec9a146-6214-4239-a817-a779d8cce6c5">

Boolean arithmatic, Boolean calculus and verilog code for different gates

<img width="349" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/04752341-6a09-4e37-bd2c-8aac2873aa28">

### Basic Mux implimentation and introduction to Makerchip
#### Multiplexer
Mux symblol and combinational circuit using gates

<img width="230" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/fc89c14e-245c-4f2b-ba50-ff9f57d1a682">
<img width="230" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ebd04009-49c0-46f4-8834-2c6d9712f42a">

Verilog for mux
``` assign f = s ? x1 : x0 ; ```

#### What is mackerchip?
Makerchip provides free and instant access to the latest tools directly from your browser and from your desktop. This includes open-source tools and proprietary ones.

Let's see one example of "pipelined FPGA multiplier" in mackerchip platform.

This is the code of pipelined multiplier

<img width="601" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/64a79ef4-0240-49a9-9e9e-2ea7bc1b947f">

Diagram of Multiplier

<img width="355" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/7baedaae-f41f-4c76-a728-e30564bcf453">

### Labs for combinational logic
#### Note:
Regarding TL-verilog

<img width="280" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/0b44497d-bbca-407f-8d0b-c871b98f3562">

#### Task (1): Writing the inverter code in mackerchip
Link for inverter: ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0pghJq```

TL verilog code for inverter is given below,

```verilog
$reset = *reset;
   
   $out = !$in ;
```

<img width="479" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ae6405ed-cba2-4700-9dd4-e0a0a11c88cf">

Now after compiling, we can see the diagram and waveform of Inverter

<img width="475" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ba23712a-2e8f-4bb2-87ea-73ec515fe445">

#### Task (2): write program regarding vectors. for example sum of 4 bit numbers,
Link for inverter: ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0qjhx9```

TL verilog code for sum of 4 bit is given below,

```verilog
$reset = *reset;
$out[4:0] = $in1[3:0] + $in2[3:0];
```

<img width="478" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/01cc1e65-7e5a-4249-9393-d185d764db61">



<img width="545" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/2b83e607-5a8a-4d2d-9ac6-325cc719581f">


Here in waveform we can see the sum of in1 and in2 at out

#### Task (3):  write program for 2x1 Mux
Link for inverter: ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0qjhx9```

TL verilog code for 2X1 Mux is given below,

```verilog
$reset = *reset;
$out[7:0] = $sel ? $in1[7:0] : $in0[7:0]; 
```

<img width="479" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/4386e918-9bca-4d1d-8b40-46ace83a526d">


Here, we are taking input is 8 bit


<img width="475" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/3e7470df-e6c5-4adc-aeeb-1e8e0f610117">



<img width="479" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/7acf84c2-3f54-40f1-a97c-6daddfcaeb0d">

Here we can see that when sel is 1 out= in1 and when sel is 0, out=in0.

#### Task (4): write a program for combinational calculator
Link of combinational calculator : ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0GZhl8#```


<img width="315" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/29bcce74-94dc-490c-bdbe-b2ca9312dc94">

we will use ```$val1[31:0] = $rand1[3:0]``` and ```$val2[31:0] = $rand2[3:0]``` for limit the input bit to 4 from 32. ```rand``` will generate 16 different combination randomly.

TL verilog Code for calculator is given below,

```verilog
m5_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   $reset = *reset;
   
   $val1[31:0] = $rand1[3:0];
   $val2[31:0] = $rand2[3:0];
   $op[1:0] = $rand3[1:0];
   
   $sum[31:0] = $val1[31:0] + $val2[31:0];
   $diff[31:0] = $val1[31:0] - $val2[31:0];
   $prod[31:0] = $val1[31:0] * $val2[31:0];
   $qout[31:0] = $val1[31:0] / $val2[31:0];
   
   $out[31:0] = ($op[1:0] == 2'b00) ? $sum[31:0] : (($op[1:0] == 2'b01) ? $diff[31:0] : (($op[1:0] == 2'b10) ? $prod[31:0] : (($op[1:0] == 2'b11) ? $qout[31:0] : 32'b0)));
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
\SV
   endmodule
```

Here i have taken,
| Function | Opcode |
| -------- | ------ |
|    Add   | 2'b00  |
|    Diff  | 2'b01  |
|    Prod  | 2'b10  |
|    Div   | 2'b11  |

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f406860f-024b-4233-ba66-2a659f5c679e">



waveform and design block for calculator is,


<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ca7d0d40-b1c2-4b46-823a-ac5daa5b3737">



## Sequential logic
### Introduction to sequential logic and Counter lab
#### Introduction to sequential logic
Sequential logic is sequenced by clock signal.
For example D-flop flop, when clock pulse will come, it will change it's state.
These sequential circuits are constructed like when reset signal came, it will goes into known state like initial state.
Any big state machine can be made by using both sequential logic and combinational logic.

<img width="245" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/a4c78843-d856-46d3-a183-300f3668264f">

#### Task (1): Fibonacci series - reset 
Link for Fibonacci series is: ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0zmhyg```

TL verilog code for Fibonacci series is given below,
```verilog
$reset = *reset;
$num[31:0] = $reset ? 1 : (>>1$num + >>2$num);
```

Here, ```>>1$num``` means first previous number and ```>>2$num``` means second previus number.

The series is: 1,1,2,3,5,8,13,21,...

And we will implement it like this,

<img width="224" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/4d4b037d-9bdc-4087-beb6-5612f75c762d">

The code in mackerchip, 

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/2f191cfd-78dd-45f6-a825-87c18fb7c02a">

#### Task (2): Counter 
Link for counter is: ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0lOh3y#```

TL verilog code for counter is given below,

```verilog
$reset = *reset;
$count[31:0] = $reset ? 0 : (>>1$count+1);
```

The counter we will implement is like this,

<img width="133" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/9dbc46ae-d0ce-482f-b840-6d2b8b099474">

The code and waveform in mackerchip is,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/e15cf1ed-8e05-4e24-bf47-1406f4fe9ff0">

### Sequential Calculator lab
In verilog we declare the values like this,

<img width="501" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/cc3b148c-f3af-488f-a0d9-3a7fd244cb66">

#### Task : Sequential calculator
Link for Sequential calculator: ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0pghJZ```

A real calculator remember the last value of calculation and it can use it for the next operation. for that we need a flip flop to remember the previous value.

When we press reset, the output should be 0.

<img width="308" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/e5641c3f-1816-4e20-af8b-87646c90435c">

we made calculator befor, but it was pure combinational. now we will do some changes in it to make sequential calculator.

As we can see the above diagram, previous output of calculator is use as a new operand for next operation.


TL verilog code for sequential calculator is given below,

```verilog
$reset = *reset;
   
   $val1[31:0] = $rand1[3:0];
   $val2[31:0] = $reset ? 0 : (>>1$out[31:0]);
   $op[1:0] = $rand3[1:0];
   
   $sum[31:0] = $val1[31:0] + $val2[31:0];
   $diff[31:0] = $val1[31:0] - $val2[31:0];
   $prod[31:0] = $val1[31:0] * $val2[31:0];
   $qout[31:0] = $val1[31:0] / $val2[31:0];
   
   $out[31:0] = ($op[1:0] == 2'b00) ? $sum[31:0] : (($op[1:0] == 2'b01) ? $diff[31:0] : (($op[1:0] == 2'b10) ? $prod[31:0] : (($op[1:0] == 2'b11) ? $qout[31:0] : 32'b0)));
   
```

Code and waveform in mackerchip is given below,

<img width="959" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/d1920a59-fa0f-444b-b612-b1fe9625fd35">


## Pipelined logic
### Pipelined logic and Retiming
#### Simple pipeline
Let's understand the simple pipeline logic by pythagoras theorem,

Link for Pythagoras theoram : ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0Elhz2#```

<img width="146" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/2779e7ea-f818-49b3-8fbc-ac1f3a5888ae">

Without pipeline it is calculated like this in single stage,

<img width="259" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f78f1235-e7a3-42e1-9d06-22274e5615c2">

Now using pipelining, we distributed it into 3 stages. After every stage, one latch or flip-flop should be available to store the value of previous stage until next stage is not ready to talk the value from previous stage.

<img width="269" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/1fd4cf35-5150-4078-a7ed-3630f6a9a071">

Here we are calculating both the square at in same stage but it is safe to calculate the both square in different stage like this,

<img width="329" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/1a12f58e-c791-4f1b-b023-c260f52b6681">


TL verilog code of Pythagoras theorem is given below,

```verilog
`include"sqrt32.v"
\TLV
   $reset = *reset;

   |calc      
      @1 
         $aa[31:0] = $rand1[3:0];
         $aa_sq[31:0] = $aa[31:0] * $aa[31:0];
      @2
         $bb[31:0] = $rand2[3:0];
         $bb_sq[31:0] = $bb[31:0] * $bb[31:0];
      @3
         $cc_sq[31:0] = $aa_sq + $bb_sq;
      @4
         $cc[31:0] = sqrt($cc_sq);
```


Here, we need to add lybrary for square roor by ``` `include "srqt32.v" ```
Here, ```|calc```  construct allows you to express this calculation concisely within the TL-Verilog code.

Code and waveform in mackerchip is given below,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/2c5c6c1e-7365-4e51-bdad-2f8b7a5747b7">


### Pipeline logic advantages and Demo in plateform
#### Advantage(1)
If we use more stages in pipeline then we can use high frequency clock.

Here we can see the example of 1 stage and 3 stage pipeline for same circuit, 

<img width="414" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/78446152-41c5-44b1-875f-a59bcf57907d">

We can see that the frequency in 3 stage clock is higher than 1 stage.

#### Advantage(2)
we can use previous stage values after many stages like this,

<img width="371" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/9683ae24-ea75-4ff6-87a0-ef15f043c878">

By using ```>>4$aa[31:0]``` we can use value of "clock 0 aa" at "clock 4 aa"

<img width="425" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/66e65645-5eb6-404a-b0ab-c5351a457f57">


### Lab on error conditions within computation pipeline
#### Identifier and Types in TL verilog
Types of identifier is determined by simbol prefix and case/delimitation style. like given below

<img width="154" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b79e4904-1a31-482a-b2f1-78a19f41f928">

The first token should be start by 2 small alphabets and then we can use any other number or alphabet.

<img width="263" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/967760e6-c15f-4fe3-9e94-2ce807fe0ce0">

#### Errors

<img width="544" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/1f37bd63-59f1-4e36-b279-1baf5badecc6">

Red circle is for ```unassigned input``` and blue circle for ```ORs``` (ORs means we give two or more error condition at a same time in one block).

### Lab on 2-Cycle Calculator
#### Task(1): Counter and calculator together in pipeline at 1 stage
Link of Counter and calculator together in pipeline at one stage: ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0Q1hpE```

<img width="300" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/1c81c16b-0787-4ed7-b5f4-cdff1b4a5227">

Here we can see the counter and calculator are together at stage @1 in "|calc".

TL verilog code for Counter and calculator together in pipeline is given below,
```verilog
$reset = *reset;
   
   |calc
      @1
         $reset = *reset;
   
         $val1[31:0] = $rand1[3:0];
         $val2[31:0] = $reset ? 0 : (>>1$out[31:0]);
         $op[1:0] = $rand3[1:0];
   
         $sum[31:0] = $val1[31:0] + $val2[31:0];
         $diff[31:0] = $val1[31:0] - $val2[31:0];
         $prod[31:0] = $val1[31:0] * $val2[31:0];
         $qout[31:0] = $val1[31:0] / $val2[31:0];
   
         $out[31:0] = ($op[1:0] == 2'b00) ? $sum[31:0] : (($op[1:0] == 2'b01) ? $diff[31:0] : (($op[1:0] == 2'b10) ? $prod[31:0] : (($op[1:0] == 2'b11) ? $qout[31:0] : 32'b0)));
      
         $count[31:0] = $reset ? 0 : (>>1$count+1);
```

code and output of macker chip,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/615dbb93-69a3-4384-b1bd-dc6f00f4c6a0">

#### Task(2): 2-cycle calculator
Link of 2-cycle calculator: ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0Vmh6l```

<img width="305" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/00021cb4-8ef9-4a66-accf-6210b1cbb90a">

Here we can see the 2 stages of calculator to operate it at high frequency and we made some changes in calculator allignment also.

Due to 2 stages, output after 2 stage should be going back to operand.

We change counter to single bit counter to indicate every clock cycle.(it will toggle between 0 and 1 at every clock cycle)

we are connecting ```$valid``` to remove or clear alternate output. means when invalide cycle will come it will reset the mux.

TL code for 2-cycle calculator is given below,
```
`include"sqrt32.v"
\TLV
   
   |calc
      @1
         $reset = *reset;
         
         $val1[31:0] = $ran1[3:0];
         $val2[31:0] = $reset ? 0 : (>>2$out[31:0]);
         $op[1:0] = $rand3[1:0];
         
         $sum[31:0] = $val1[31:0] + $val2[31:0];
         $diff[31:0] = $val1[31:0] - $val2[31:0];
         $prod[31:0] = $val1[31:0] * $val2[31:0];
         $qout[31:0] = $val1[31:0] / $val2[31:0];
         $valid = $reset ? 32'b0 : (>>1$valid + 1);
      @2
         $out[31:0] = ($reset | (!$valid)) ? 32'h0 : (($op[1:0] == 2'b00) ? $sum[31:0] : (($op[1:0] == 2'b01) ? $diff[31:0] : (($op[1:0] == 2'b10) ? $prod[31:0] : (($op[1:0] == 2'b11) ? $qout[31:0] : 32'b0))));
   
```

Code and waveform from mackerchip is given below,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b7a7e994-49bd-4b71-8976-887c597c609b">



## Validity
### Introduction to Validity and its advantages
#### Validity
In TL-Verilog (Transaction-Level Verilog), "validity" refers to a concept related to the state of a transaction or data transfer. In transaction-level modeling, you often have data that needs to be transferred from one block or module to another, and it's important to track whether the data is valid or not.

It's represented by a signal, often named valid, which can have two values: 1 (true) to indicate that the data is valid, or 0 (false) to indicate that the data is not valid or not ready.

Validity signals help manage data flow, synchronization, and correctness in transaction-level hardware descriptions. They ensure that data is processed only when it's in a valid state, helping to maintain the integrity of the design.

#### Advantages of Validity
(1) Easy to debug the code 

(2) Design become clean 

(3) Error checking become more better

(4) Automated clock getting

#### What is clock getting?
Clock getting is power saving feature. Lots of power consumption comming from clock circuit.

clock gating is a technique used to optimize the power efficiency of digital integrated circuits. 

It involves inserting logic gates into the clock network to selectively disable or "gate" the clock signal to certain areas of the chip when they are not in use. 

This helps reduce dynamic power consumption by preventing unnecessary clock toggling in idle or unused portions of the circuit. 

Clock gating is a common practice in modern chip design to improve energy efficiency without sacrificing performance.

Basically it is avoids the toggling of every clock at everytime.

### Lab on Validity and valid when condition
#### Task: validity in pipeline of pythagoras theorem.

Link for the pipelinig of pythagoras theorem with validity : ```https://www.makerchip.com/sandbox/0XDfnhVvQ/01jhoB#```

TL verilog code is given below,
```verilog
   `include"sqrt32.v"

\TLV
   
   // Stimulus
   |calc
      @0
         $valid = & $rand_valid[1:0];  // Valid with 1/4 probability
                                       // (& over two random bits).
   
   // DUT (Design Under Test)
   |calc
      ?$valid
         @1
            $aa_sq[7:0] = $aa[3:0] ** 2;
         @2
            $bb_sq[7:0] = $bb[3:0] ** 2;
         @3
            $cc_sq[8:0] = $aa_sq + $bb_sq;
         @4
            $cc[4:0] = sqrt($cc_sq);


   // To Print output in log
   |calc
      @4
         \SV_plus
            always_ff @(posedge clk) begin
               if ($valid)
                  \$display("sqrt((\%2d ^ 2) + (\%2d ^ 2)) = \%2d", $aa, $bb, $cc);
            end
```

Here, we are enabling a valid bit when rand_valid = 3.

code and waveform from mackerchip,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/80bfd981-96cb-4f0a-86b4-d779e08cb60c">


### Lab to commpute total distance
#### Task: Distance accumulator with validity
Link for distance accumulator with validity : ```https://www.makerchip.com/sandbox/0XDfnhVvQ/098hXZ```
We will create a distance accumulator by tracking the total distance travel in a series of "hopes", depicted in a RED line in a figure given below.

<img width="134" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/c06de247-f7ba-4313-b79c-fb59700a7847">

So these pipeline is looks like this,

<img width="287" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/32f42223-eae1-4e0b-830e-bf57957bbb19">

Here when reset come, total distance become 0. when valid signal come, mux will take value from adder. and when valid signal will not come, at that time mux will stuck at previous total distance at output.

TL verilog code for this is given below,
```verilog
  `include"sqrt32.v"

\TLV
   
   // Stimulus
  
   |calc
      @1
         $reset = *reset;
      
      ?$valid
         @1 
            $aa[31:0] = $rand1[3:0];
            $aa_sq[31:0] = $aa[31:0] * $aa[31:0];
            $bb[31:0] = $rand2[3:0];
            $bb_sq[31:0] = $bb[31:0] * $bb[31:0];
         @2
            $cc_sq[31:0] = $aa_sq + $bb_sq;
         @3
            $cc[31:0] = sqrt($cc_sq);
      @4
         $tot_dist[63:0] = $reset ? 64'b0 : ($valid ?
                (>>1$tot_dist + $cc) : $RETAIN); 
                  //$RETAIN = >>1$tot_dist
```

Here we use ```$RETAIN = >>1tot_dist```.

Code and waveform form mackerchip is given below,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/bcba4e37-44df-45da-9a93-3b97b83c57fd">


### Lab on 2-Cycle Calculator with validity
Link for 2-cycle calculator with  validity is :```https://www.makerchip.com/sandbox/0XDfnhVvQ/0j2hX5#```

Previously what we are doing it is when invalid signal come, the mux is going to be reseted. but now we use valid signal to validet the output.

<img width="292" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/176062f9-7e2e-4d94-ae74-472a00b477b1">

TL verilog code for 2-cycle calculator with validity is given below,
```verilog
   `include"sqrt32.v"

\TLV
   
   // Stimulus
  
   $reset = *reset;
   
   $val2[31:0] = $rand4[3:0];
   
   |calc
      @1
         $reset = *reset;
         
         $val1[31:0] = $rand1[3:0];
         $val2[31:0] = >>2$out;
         $op[1:0] = $rand3[1:0];
         $valid = $reset ? 0 : >>1$valid+1;
         $valid_or_reset = $valid || $reset; 
      ?$valid_or_reset
         @1
            $sum[31:0] = $val1+$val2;
            $diff[31:0] = $val1-$val2;
            $prod[31:0] = $val1*$val2;
            $div[31:0] = $val1/$val2;
            
         @2
            $out[31:0] = ($reset) ? 32'h0 : (($op[1:0] == 2'b00) ? $sum[31:0] : (($op[1:0] == 2'b01) ? $diff[31:0] : (($op[1:0] == 2'b10) ? $prod[31:0] : (($op[1:0] == 2'b11) ? $qout[31:0] : 32'b0))));
   
```
##### Note: Here, when reset is not equal to zero at that time whole block will run.
Code and waveform form mackerchip is given below,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/121eba67-bf69-4f0d-9475-43b32af9e8a7">

### Calculator Singal value Memory lab
Link of calculator single value memory is : ```https://www.makerchip.com/sandbox/0XDfnhVvQ/0oYhRw```

Calculators supports "mem" and "recall" to remember and recall the values.

<img width="309" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/708336a1-0e09-4492-afb0-580b9e4adbad">

For this memory and recall we have do some modification in previos 2-cycle calculator. 

These modifications are (1) change "$op[1:0]" to "$op[2:0]" means now opration can be 9. (2) we have to add one memory mux to store the bit. (3) select recall value in output mux. means when recall signal come, output mux will stuck at output value of memory mux.

TL code for calculator singal value memory is given below,
```
   `include"sqrt32.v"

\TLV
   
   // Stimulus
  
  |calc
      @1
         $reset = *reset;
         $val1 [31:0] = >>2$out;
         $val2 [31:0] = $rand2[3:0];
         $valid = $reset ? 1'b0 : >>1$valid + 1'b1 ;
         $valid_or_reset = $valid || $reset;

      ?$vaild_or_reset
         @1   
            $sum [31:0] = $val1 + $val2;
            $diff[31:0] = $val1 - $val2;
            $prod[31:0] = $val1 * $val2;
            $div[31:0] = $val1 / $val2;

         @2   
            $mem[31:0] = $reset ? 32'b0 :
                         ($op[2:0] == 3'b101) ? $val1 : >>2$mem ;

            $out [31:0] = $reset ? 32'b0 :
                          ($op[2:0] == 3'b000) ? $sum :
                          ($op[2:0] == 3'b001) ? $diff :
                          ($op[2:0] == 3'b010) ? $prod :
                          ($op[2:0] == 3'b011) ? $quot :
                          ($op[2:0] == 3'b100) ? >>2$mem : >>2$out ;

```

##### Here, when reset is not equal to zero at that time whole block will run. when op=4 at that time output will give memory value of 2 previous stage othervise output will give 2 previous value of output. when op=5, memory= $val1 othervise always memory= 2 previous value of memory (memory is always in a loop with 2 previous value of memory except op=5).

code and waveform from mackerchip is given below,

<img width="958" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/332f93b5-79cd-4f49-963d-8d58d41442ac">



## Wrap up
### LINK OF MACKERCHIP EXAMPLES WITH TUTIRIALS : ```https://myth.makerchip.com/sandbox?code_url=https:%2F%2Fraw.githubusercontent.com%2Fstevehoover%2FRISC-V_MYTH_Workshop%2Fmaster%2Freference_solutions.tlv```




# Day 4 -Basic RISC-V CPU Micro-architecture
## Introduction to simple RISC-V Micro-architecture
### Micro-architecture of single cycle RISC-V CPU
Basic Block diagram (micro-architecture) of RISC-v CPU is given below,

<img width="390" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/cc734131-013a-479e-9057-2b5479f3357d">

Lets see every component one by one.

#### (1) PC (program counter)
A Program Counter (PC), also known as an Instruction Pointer (IP) in some architectures, is a special-purpose register or hardware component used in computer processors to keep track of the address of the next instruction to be executed in a program. It plays a crucial role in the execution of instructions in a computer's CPU.

#### (2) Instruction memory
Instruction memory, also known as the instruction cache or instruction memory unit, is a component within the central processing unit (CPU) of a computer that is responsible for storing and providing access to the instructions that the CPU needs to execute a program. It is a fundamental part of the CPU's architecture and plays a key role in the execution of computer programs.

#### (3) Instruction decoder
An Instruction Decoder is a critical component within the CPU of a computer. Its primary function is to interpret and decode the machine instructions fetched from memory and prepare them for execution by the CPU's execution units. It decodes the binary representation of the instruction and generates control signals that govern the operation of other components in the CPU to execute the instruction.

#### (4) Register file read (RF Rd)
RF RD is a component that stores a set of registers used to hold data during the execution of instructions. Instructions often involve reading data from these registers. The instruction specifies which registers to read, and the data from these registers can be used as operands for operations performed by the ALU or other components.

#### (5) Register file write (RF Wr)
The write register file is responsible for storing the results of operations back into registers. After an instruction is executed, the result is often written back to the register file. This ensures that the updated data is available for subsequent instructions.

#### (6) Data memory 
The data memory is a storage component used to store data that is manipulated by instructions during program execution. Unlike instruction memory, data memory can be both read from and written to. It holds variables, data arrays, and other information that the program uses during its execution.

#### (7) ALU
The ALU is a fundamental digital circuit within the CPU that performs arithmetic and logical operations on data. It can perform tasks such as addition, subtraction, multiplication, division, bitwise operations (AND, OR, XOR), and comparisons. The ALU generates results that are used in various computations specified by the instructions.


### Starting point code for RISC-V labs part-1

Vedio Link for this stages : ```https://myth.makerchip.com/sandbox?code_url=https:%2F%2Fraw.githubusercontent.com%2Fstevehoover%2FRISC-V_MYTH_Workshop%2Fmaster%2Frisc-v_shell.tlv#```

Code link for this stages : ```https://myth.makerchip.com/sandbox?code_url=https:%2F%2Fraw.githubusercontent.com%2Fstevehoover%2FRISC-V_MYTH_Workshop%2Fmaster%2Frisc-v_shell.tlv#```

If we go there and make comment off (example, remove the "//") then in diagram we will see the step by step changes.


### Starting point code for RISC-V labs part-2

Link of reference solution : ```https://myth.makerchip.com/sandbox?code_url=https:%2F%2Fraw.githubusercontent.com%2Fstevehoover%2FRISC-V_MYTH_Workshop%2Fmaster%2Freference_solutions.tlv#```

In this reference solution we can see the total block diagram of RISC-V and also see the visulization of RISC-V.


## Fetch and decode
### Implementation plan and lab for PC
#### Implementation plan
The implementation plan of RISC-v in pipeline like this,

<img width="314" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/87e6aacd-c731-4830-a78d-75f75ce354e6">

In 3 stage we will implement this RISC-V. We will implement RISC-V CPU in the sequence of given number in above plan. like (PC) >> (IMemRd) >> (Dec) >> (RF Rd) >> (ALU) >> (RF Rw) >> (Branch Target computation)

#### Task: Reset the $pc[31:0] to 0 if previous instruction was a "reset instruction"(>>1$reset), and increment by 1 instruction (32'd4 bytes) thereafter(means current instruction is to add 4 in Previous value of PC). ```NOte``` we will add branch support letter. till now just PC for next instruction.  
We have to write the code in ```https://myth.makerchip.com/sandbox?code_url=https:%2F%2Fraw.githubusercontent.com%2Fstevehoover%2FRISC-V_MYTH_Workshop%2Fmaster%2Frisc-v_shell.tlv#```


<img width="375" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/99a9cb62-d824-4d09-a25d-17f3fea7f434">

Link for PC next is: ```https://myth.makerchip.com/sandbox/01wfphG9Q/0JZhOK``` 

TL verilog code for PC is given below,
```verilog
    m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;



         $pc[31:0] = >>1$reset ? 32'd0 : (>>1$pc + 32'd4);

      // Note: Because of the magic we are using for visualisation, if visualisation is enabled below,
      //       be sure to avoid having unassigned signals (which you might be using for random inputs)
      //       other than those specifically expected in the labs. You'll get strange errors for these.

   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
```

Block diagram and waveform from mackerchip,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/31fd6db3-79ca-4214-8e3a-fdce377caaad">


After the simulation, here we can see that the "$pc[31:0]" become 0,4,8...


### Labs for intruction Fetch logic
#### Task : implementing instruction fetch
Link for fetch implementatin is : ```https://myth.makerchip.com/sandbox/01wfphG9Q/00ghvV```

Till now we implemented PC logic. now next step is to implement fetch logic.
In the shell(which is given by the starter code), provides the instruction memory (means the memory is instruntiated in the shell). So, first we have to uncomment the "//m4+imem(@1)" and "//m4+cpu_viz(@4)" [m4+cpu_viz(@4) will open the visulization in the mackerchip].

After that we can see the iMem block in the block diagram.

<img width="959" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f81147c1-489c-4532-9f8d-fbd03e4589ff">

Now  let's implement fetching of instruction from memory. 

<img width="151" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/97e753c6-da51-4cf2-96fc-1395ebf997d2">

For that we have to write program like this,

<img width="283" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/54fcc254-cb6b-4a7e-87f5-4f7cdcc230ad">

Now in fatching Instruction from memory, memory block expect some the inputs like "memory read enable", "memory read address" and memory block will give output as "memory read data".

Now we have to connect memory block to the $pc[31:0] for address of instruction.
Here we are writing [M4_IMEM_INDEX_CNT-1:0] means the range of memory address bit. i.e., if memory address=5 bit then [M4_IMEM_INDEX_CNT-1:0] = [4:0]. for that "M4_IMEM_INDEX_CNT" is declared first. 

Now, [M4_IMEM_INDEX_CNT+1:2] means every PC value is 32 bit number. so every next instruction address will be 4 times bigger then current address. so here by shifting 2 bit right side, we are multiplying current address by 4 times and giving new address from pc.

TL verilog Code for this is given below,
```verilog
\TLV

   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Program for MYTH Workshop to test RV32I
   // Add 1,2,3,...,9 (in that order).
   //
   // Regs:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): 10
   //  r13 (a3): 1..10
   //  r14 (a4): Sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   
   // Optional:
   // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;



         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
      @1
         // Instruction Fetch 
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_en ? $imem_rd_data[31:0] : 32'b0;
         `BOGUS_USE($instr)

      // Note: Because of the magic we are using for visualisation, if visualisation is enabled below,
      //       be sure to avoid having unassigned signals (which you might be using for random inputs)
      //       other than those specifically expected in the labs. You'll get strange errors for these.

   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      //m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
      //m4+myth_fpga(@0)  // Uncomment to run on fpga

   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
\SV
   endmodule
```

Code and waveform from mackerchip is given below,

<img width="956" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b0bdcf21-fdbe-4142-beb0-ae31d72d8439">




### Lab for RV instruction Types IRSBJU decode logic
#### instruction type decode
In 32 bit instruction, instr[6:2] (5bit) shows the types of instruction like, I,R,S,B,J,U.  OPCODE IS 7 BIT [6:0] in  total instruction. except this 5 bit [6:2], other 2 bits are always "11" for base types instruction.

<img width="424" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/0fa8393b-c639-426e-919d-8a2f7f6498aa">

In upper image code, we define the i type(immediate type) intructions.

### Lab for instruction immediate decode logic for RV-ISBUJ
Let's see different types of instruction (I,R,S,B,J,U).

<img width="485" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/9d60ed4f-860a-4881-a01c-99862425d84f">

In immediate type instruction, Immediate bit = last 12 bit from instruction([31:20]). But $imm[31:0] is 32 bit. To full this immediate vector, we are copy first 11 bit [30:20] in last 11 bit($imm[10:0]) of $imm[31:0] vector and repeat that 31th bit of instruction vector($istr[31:0]) 21 times to fill the other 21 bits ($imm[31:11]) of $imm[31:0] vector.


### Labs to decode other fields of instruction for RV-ISBUJ
#### Instruction decode
Let's extract the other file like $func7,$fuct3,$rs1, $rs1,$rd and $opcode.

<img width="565" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/0f04993d-90c0-4693-be1f-0f458470b538">

### Labs to decode instruction field based on Instr type RV-ISBUJ
In upper table we can see that "rs2" is needed only in R,S and B type intruction. So for the we have to create valid condition.

<img width="499" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f400b397-af72-4d01-9a1c-da64824dfdad">

This valid bit syntax is: ```$rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
                          ?$rs2_valid      
                           $rs2[4:0] = $instr[24:20];      
                          ``` 


### Labs to decode individual instruction
Here we are just decoding the relevent instruction in our perticular test program.

<img width="356" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/f2f5b2c8-96b8-4bba-b59a-5d7f8d52cad4">

Here we can see the use of "$func7" , "$func3" and opcode.

Let's see the example of instruction "BEQ"

<img width="214" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b0e644d0-c91c-4f4e-9722-408d182ac147">

### Labs of complete instruction decode
Link of instruction decode is : ```https://myth.makerchip.com/sandbox/01wfphG9Q/0Y6h41#```

TL verilog code for Instruction decode is given below,
```verilog
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

|cpu
      @0
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
      @1
         // Instruction Fetch
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_en ? $imem_rd_data[31:0] : 32'b0;
      @1
         //Instruction Decode
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||   // ==? is used to compare the binary don't cares
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? {$instr[31:12], 12'b0} :
                      $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         $opcode[6:0] = $instr[6:0];
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
            
         $dec_bits [10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         `BOGUS_USE($is_beq $is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
      //`BOGUS_USE is a system verilog signgle argument macro to silence the warning is assigned but never used.
      
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      //m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
      //m4+myth_fpga(@0)  // Uncomment to run on fpga

   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
\SV
   endmodule
```

Code and block diagram from mackerchip is given below,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ae1d8a0a-a909-4353-b13f-eea2721bab3e">






## RISC-V control logic
### Lab for register file read part-1
#### TASK: Implementation of register file read (RF Rd)
<img width="472" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/3cd7a39c-4f8e-4556-b37b-be8e2c074a93">

Upto now we decoded the instructions. Now based on instruction we have to read the oprand value from register file using decode bits like "$rs1","$rs2"(both rs1 and rs2 have address of register file).

This register file is already implemented in our shell. so we have to uncomment the syntax "//m4+rf(@1,@1)". and we have to give proper input signals to rf block like $reset, $rf_wr_en, $rf_rd_en1, $rf_rd_en2,etc.

<img width="317" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/68c65f3d-304b-4fd1-85cc-636232ea62a9">

### Lab for register file read part-2
Now we are assigning the read data from register file to $src1/2_value[31:0]. These signals we will gives to input in ALU.

Link for register file read is :```https://myth.makerchip.com/sandbox/01wfphG9Q/0O7hyl#```

TL verilog code for register file read is given below,
```verilog
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
      @1
         // Instruction Fetch
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_en ? $imem_rd_data[31:0] : 32'b0;
         
      @1
         //Instruction Decode
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||   // ==? is used to compare the binary don't cares
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? {$instr[31:12], 12'b0} :
                      $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         $opcode[6:0] = $instr[6:0];
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
            
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         `BOGUS_USE($is_beq $is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
      //`BOGUS_USE is a system verilog signgle argument macro to silence the warning is assigned but never used.
         
      @1
         //Register File Read
         
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;
         
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;
         
         $src1_value[31:0] = $rf_rd_data1;
         $src2_value[31:0] = $rf_rd_data2;
         `BOGUS_USE($src1_value $src2_value)
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
      //m4+myth_fpga(@0)  // Uncomment to run on fpga

   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
\SV
   endmodule
```

code and waveform from macherchip is given below,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b86c0c2f-0031-4b41-b5ac-c2b1f99da25a">



### Lab for ALU operations for add/addi
#### Task: Implementation of ALU
Link for AlU is : ```https://myth.makerchip.com/sandbox/01wfphG9Q/0RghzP#```
We taken output $src1_value[31:0] and $src2_value[31:0] from register file. now we give this data as an input to ALU block.

<img width="476" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/aa68297d-480c-48a0-ba19-375c50b9f89c">

Now we will write the syntax for addi and add for ALU.

Syntax for add/addi is : ```
                         $result[31:0] = $is_add ? ($src1_value[31:0] + $src2_value[31:0]) :
                                         $is_addi ? ($src1_value[31:0] + $imm[31:0]):
                                         32'b0;
                         ```    

TL verilog code is given below,
```verilog
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
      @1
         // Instruction Fetch
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_en ? $imem_rd_data[31:0] : 32'b0;
         
      @1
         //Instruction Decode
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||   // ==? is used to compare the binary don't cares
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? {$instr[31:12], 12'b0} :
                      $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         $opcode[6:0] = $instr[6:0];
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
            
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         `BOGUS_USE($is_beq $is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
      //`BOGUS_USE is a system verilog signgle argument macro to silence the warning is assigned but never used.
         
      @1
         //Register File Read
         
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;  //m4+rf(@1, @1) takes input $rf_rd_index1[4:0] (which is index value of register of RISC-V)
                                     // and return its value as $rf_rd_data1 of 32 bit, which is the value stored in that register
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;  //m4+rf(@1, @1) takes input $rf_rd_index1[4:0] (which is index value of register of RISC-V)
                                     // and return its value as $rf_rd_data2 of 32 bit, which is the value stored in that registe
         $src1_value[31:0] = $rf_rd_data1;
         $src2_value[31:0] = $rf_rd_data2;
      @1
         //ALU Implementation
         $result[31:0] = $is_add ? ($src1_value[31:0] + $src2_value[31:0]) :
                         $is_addi ? ($src1_value[31:0] + $imm[31:0]):
                         32'b0;
         `BOGUS_USE($result)
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
      //m4+myth_fpga(@0)  // Uncomment to run on fpga

   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
\SV
   endmodule
```

code and waveform from mackerchip is given below,
<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/81f767e0-d766-4633-8306-794661a6e475">


### Lab for register file write
#### Task: Implemetation of register file write
Link for register write is:```https://myth.makerchip.com/sandbox/01wfphG9Q/066hBL#```

<img width="491" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/613cc481-5ab8-488c-82c1-2cc25a9d7f94">

We already have register file in a shell. now we have to give some input to register file to write back lime $rd_wr_en, $rf_wr_index[4:0] and $rf_wr_data[31:0].

<img width="318" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/1f5bc12e-0877-4ab7-be08-ed92d3f6cdc7">

In RISC-V, X0 register is always 0. so we can not write anything there. so we have to disable writing X0. syntax for that is ```$rf_wr_en = $rd_valid && $rd != 5b'0```

TL varilog code for this is given below,
```
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
      @1
         // Instruction Fetch
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_en ? $imem_rd_data[31:0] : 32'b0;
         
      @1
         //Instruction Decode
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||   // ==? is used to compare the binary don't cares
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? {$instr[31:12], 12'b0} :
                      $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         $opcode[6:0] = $instr[6:0];
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
            
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
         `BOGUS_USE($is_beq $is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
      //`BOGUS_USE is a system verilog signgle argument macro to silence the warning is assigned but never used.
         
      @1
         //Register File Read
         
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;  //m4+rf(@1, @1) takes input $rf_rd_index1[4:0] (which is index value of register of RISC-V)
                                     // and return its value as $rf_rd_data1 of 32 bit, which is the value stored in that register
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;  //m4+rf(@1, @1) takes input $rf_rd_index1[4:0] (which is index value of register of RISC-V)
                                     // and return its value as $rf_rd_data2 of 32 bit, which is the value stored in that registe
         
         $src1_value[31:0] = $rf_rd_data1;
         $src2_value[31:0] = $rf_rd_data2;
      @1
         //ALU Implementation
         $result[31:0] = $is_add ? ($src1_value[31:0] + $src2_value[31:0]) :
                         $is_addi ? ($src1_value[31:0] + $imm[31:0]):
                         32'b0;
      @1
         // Register write back
         $rf_wr_en = $rd_valid && $rd != 5'b0;
         $rf_wr_index[4:0] = $rd;                              // $rd=0(because x0 register of RISC-V always stores vale 32'b0 so can't be rewritten ) 
         $rf_wr_data[31:0] = $result[31:0];
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
      //m4+myth_fpga(@0)  // Uncomment to run on fpga

   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
\SV
   endmodule

```
Code and waveform form mackerchip is given below,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/4d7d9fce-a60f-4cdb-81c0-fb283ff53082">



### Concept of Array and Register file details
#### what is inside the register file?

<img width="484" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/040aa1f9-6d0d-4947-a819-db282e02c763">

In this image we can see how we read 32 bit data from register filr. here there are 32 blue boxes are available for every registers. according to index of register and anable signal MUX will select the input and give it as output.

<img width="488" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/cb23fcbb-b7ce-4026-9f71-e67a0a4443c0">

Now during writing time, after every clock pulse, register file update the new value which was taken from previos stage.


### Labs for Implementing branch instructions



<img width="445" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/9d3fbc0c-35de-4470-9e19-d5afeed927b7">

Branch instruction is conditional instruction. means when condition is satisfied then only we will take the branch. This condition is computed based on some registers. 

Branch and jump both are different in RISC_V. Branch is conditional where jump is unconditional. 

We have 6 operations regarding branch.

<img width="239" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/cfd949d4-39bf-4b71-80da-5d797d65e4c5">

We have to code all these 6 condition into $taken_br with condition.

### Labs for complementing branch instructions implementaion
#### Task: implemnting branch instruction
Link for branch instruction is :```https://myth.makerchip.com/sandbox/01wfphG9Q/0lOhvK```

When branch instruction is taken, we have to update the PC = PC + immidiate which will gives you the address of next instruction. and we have to modify the $pc MUX expression to use previous $br_tgr_pc when the previous intruction was branch taken.

TL verilog code for branch instruction is given below,
```verilog
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'd0 : (>>1$taken_branch ? >>1$br_tgt_pc :  (>>1$pc+32'd4));
      @1
         //Branch Instructions
         $taken_branch = $is_beq ? ($src1_value == $src2_value): //branch equal 
                         $is_bne ? ($src1_value != $src2_value): //branch unequal 
                         $is_blt ? (($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31])): //branch less than
                         $is_bge ? (($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31])): //branch greater than equal
                         $is_bltu ? ($src1_value < $src2_value): //branch unsigned less than
                         $is_bgeu ? ($src1_value >= $src2_value): //branch unsigned greater than equal
                                    1'b0;
         `BOGUS_USE($taken_branch)
         $br_tgt_pc[31:0] = $pc + $imm;
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
      //m4+myth_fpga(@0)  // Uncomment to run on fpga

   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
\SV
   endmodule
```

Code and block diagram from mackerchip is given below,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/2a11cdc0-6878-4a52-89b0-8c6e21a73cc3">

### Full RISC-V architecture with testbench
```Note:```We are applying the testbench here to tell Makerchip when simulate passes by monitoring the value of register x10 containing the sum (within@1). It will return the passed message in log file if register x10 contains the correct sum value.


Link of full RISC-V architecture is: ```https://myth.makerchip.com/sandbox/0rkfAhzM5/0xGhAD#```

TL verilog code for RISC-V architecture is given below,
```verilog
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/BalaDhinesh/RISC-V_MYTH_Workshop/master/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV

   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Program for MYTH Workshop to test RV32I
   // Add 1,2,3,...,9 (in that order).
   //
   // Regs:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): 10
   //  r13 (a3): 1..10
   //  r14 (a4): Sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   
   // Optional:
   // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'd0 : (>>1$taken_branch ? >>1$br_tgt_pc :  (>>1$pc+32'd4));
      @1
         // Instruction Fetch
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];     // $imem_rd_addr is going to m4+imem(@1) vinding the vakue of that address    
         $instr[31:0] = $imem_rd_en ? $imem_rd_data[31:0]: 32'b0;             // and returning it in $imem_rd_data[31:0]
      @1
         //Instruction Decode
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||   // ==? is used to compare the binary don't cares
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? {$instr[31:12], 12'b0} :
                      $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         $opcode[6:0] = $instr[6:0];
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
            
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
      @1
         //Register File Read
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;  //m4+rf(@1, @1) takes input $rf_rd_index1[4:0] (which is index value of register of RISC-V)
                                     // and return its value as $rf_rd_data1 of 32 bit, which is the value stored in that register
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;   //m4+rf(@1, @1) takes input $rf_rd_index1[4:0] (which is index value of register of RISC-V)
                                     // and return its value as $rf_rd_data2 of 32 bit, which is the value stored in that register
         $src1_value[31:0] = $rf_rd_data1;
         $src2_value[31:0] = $rf_rd_data2;
      @1
         //ALU
         $result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx ;
      @1
         //Register File Write                  // $rd_valid = 1 when ISA have rd its instruction 
         $rf_wr_en = $rd_valid && $rd != 5'b0;  // if $rd_valid =0 or $rd =0 then then $rf_wr_en is 0
         $rf_wr_index[4:0] = $rd;                              // $rd=0(because x0 register of RISC-V always stores vale 32'b0 so can't be rewritten ) 
         $rf_wr_data[31:0] = $result;       // $result is coming from ALU and getting stored in $rf_wr_index[4:0] address of RISC-V register         
                                            // having value $rf_wr_data   
      @1
         //Branch Instructions
         $taken_branch = $is_beq ? ($src1_value == $src2_value):               //BEQ (Branch if Equal)
                         $is_bne ? ($src1_value != $src2_value):               //BNE (Branch if Not Equal)  
                         $is_blt ? (($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31])):    // BLT (Branch if Less Than)
                         $is_bge ? (($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31])):   //BGE (Branch if Greater Than or Equal)
                         $is_bltu ? ($src1_value < $src2_value):              //BLTU (Branch if Less Than Unsigned)
                         $is_bgeu ? ($src1_value >= $src2_value):             //BGEU (Branch if Greater Than or Equal Unsigned)
                                    1'b0;                 
         $br_tgt_pc[31:0] = $pc + $imm;
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = |cpu/xreg[10]>>5$value == (1+2+3+4+5+6+7+8+9);
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
      //m4+myth_fpga(@0)  // Uncomment to run on fpga

   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
\SV
   endmodule
```

Code from mackerchip is given below,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/8c71d51e-a6b7-499b-8453-a502e683b30c">

Block diagram from mackerchip is given below,

<img width="960" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/dd3892ad-e877-4eea-9e9e-06977f91ed7e">


Waveform from mackerchip is given below,
Finally, here we are getting 45 as a result.

<img width="960" alt="Screenshot 2023-09-24 025859" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/0d3f7bb6-8016-4112-bd88-dad3706626d7">




# Day 5 -Complete pipelined RISC-V CPU micro-architecture
## Pipelining the CPU
### Introduction to Control flow Hazard and Read after write Hazard
We can understand the pipelining by waterfall logic diagram.

<img width="569" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ebcf8be3-5937-4c67-a55d-e34194fe4fd8">

#### Pipelining in RISC-V
Till now our RISC-V architecture is working currectly but it is running at low frequenccy because of single stage. Let's convert our RISC-V architecture into 5 stages, so that we can use it at high frequency. So at the end, clock speed will increase and overall performance will increase.

<img width="459" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/8a0e45a8-0c2c-4196-a6d7-5606bcea67ab">

But when we are going to connect it in 5 stages like this,

<img width="446" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/d20998cd-048e-4daa-a8cc-a536f2d359e5">

#### Control flow hazard
Some problems occurse. for example, if branch instruction came at stage 1, then in next stage we need target address immidiatly. but in as we can see in pipelined stages, the target address is calculated in registers and it will come out at stage 4. so it will crreate control flow hazard.

#### Read after write hazard
Similarly other example, if we want to write the result in register bank then second writing stage should be after first calculation stage. so here read after write hazard created.

#### Branch instruction hazard
One of the most significant hazards is the "branch instruction hazard," also known as the "branch penalty."

Branch instructions are used to alter the sequence of instructions being executed by the processor. They allow the program to make decisions, such as jumping to a different section of code depending on a certain condition. Branch instructions introduce hazards in pipelining due to the fact that the outcome of the branch (taken or not taken) is often determined later in the pipeline than the fetch and decode stages.


### Lab to create 3-Cycle valid signal
Link for valid 3-cycle signal is : ```https://myth.makerchip.com/sandbox/0rkfAhzM5/0vgh64#```

If we look at diagram in another way instrad of waterfall logic then the hazards are looks like this,

<img width="452" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/2997a659-d845-4b71-bede-3cba0cc03dce">

Suppose our pipeline have a 5 stages like this,

<img width="227" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/198f7e20-832c-49f1-92c8-14effafbd389">

Let's understand it by some specific instructions like given below.

<img width="559" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/ef8c868d-f2f6-4fdd-bb08-d6cc66ac7b85">

Let's solve this problem by two ways.

#### first solution of hazard: 3-cycle valid signal 
We operate out pipeline at every third cycle. then instructions are look like this in waterflow diagram,

<img width="569" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/1c9700ea-003e-4303-bdc6-ce76eca27573">

So, in this types of solution, pipeline latency between signals looks like this,

<img width="579" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/4cc8afa3-3854-474e-94f0-fe0d9d36a93c">

To implement this, we have to create valid signal to understand which clock cycle is valid or not.

<img width="458" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/d66d0fdc-d6e4-4f66-9931-89be7d70b701">

We have to create $valid cycle pulse loop after every 3 cycles. we have to create $valid= 0 when $reset=1,$valid=1 when $start=1 and >>3$valid(means after every third cycle $valid=1 or in other word, $valid= value that was 3 cycle before).

<img width="527" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/792223c3-87d9-4776-a6ff-d5fe474dd49d">

TL verilog code for 3-cycle valid signal is given below,
```verilog
   |cpu
      @0
         $reset = *reset;
         $start = (>>1$reset && !$reset) ;
         $valid = $reset ?  1'b0 : ($start || >>3$valid ); 

```

Code and waveform from mackerchip,

<img width="959" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/0a4dbc97-6071-4d87-9573-af13a28d7cbb">

Here we can see the same output signal as we saw upper.



### Lab to code 3-Cycle RISC-V to take care of invalid Cycles
Link for 3-cycle RISC-V is : ```https://myth.makerchip.com/sandbox/0rkfAhzM5/0Z4hZg#```

<img width="523" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/a4e280fe-7215-45fa-bf94-e74193322741">

Here we have to take care of things like,

<img width="535" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/79c186a4-1825-4475-ae3e-ea6f660f53ac">

Here we have to avoid Writing in RF during invalid clock. for that we have to introduce $rf_wr_en = $valid && $rf_wr_en1; where $rf_wr_en1 =$rd_valid && $rd != 5'b0; (if $rd_valid =0 or $rd =0 then then $rf_wr_en1 is 0). Here we are changing $rf_wr_en to $rf_wr_en1 because bydefault $rf_wr_en is given to RF. so we have to take other variable.

Next step is to avoid PC to redirecting during invalid instruction(Invalid instruction=instruction at invalid signal). to to that we have to create signal called $valid_taken_br = $valid && $taken_br . means when valid signal will come at that time only branch insruction will perform and update the PC with calculated traget address. For this signal we give to PC mux to control the  PC mux.

In last step we have to update PC instruction by >>3.

TL verilog code for 3-cycle RISC-V is given below,
```verilog
   \m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/BalaDhinesh/RISC-V_MYTH_Workshop/master/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV

   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Program for MYTH Workshop to test RV32I
   // Add 1,2,3,...,9 (in that order).
   //
   // Regs:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): 10
   //  r13 (a3): 1..10
   //  r14 (a4): Sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   
   // Optional:
   // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         $start = (>>1$reset && !$reset);
         $valid = $reset ?  1'b0 : ($start || >>3$valid );   // to generate valid signal after every third clock
         
         $pc[31:0] = >>1$reset ? 32'd0 : (>>3$valid_taken_branch ? >>3$br_tgt_pc :  (>>3$pc+32'd4));
      @1
         // Instruction Fetch
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];     // $imem_rd_addr is going to m4+imem(@1) vinding the vakue of that address    
         $instr[31:0] = $imem_rd_en ? $imem_rd_data[31:0]: 32'b0;             // and returning it in $imem_rd_data[31:0]
      @1
         //Instruction Decode
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||   // ==? is used to compare the binary don't cares
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] ==? 5'b10100;
         
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? {{21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? {{20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? {$instr[31:12], 12'b0} :
                      $is_j_instr ? {{12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} :
                                    32'b0;
         $opcode[6:0] = $instr[6:0];
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
            
         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         ?$funct3_valid
            $funct3[2:0] = $instr[14:12];
            
         $funct7_valid = $is_r_instr ;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];
            
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits ==? 11'b0_000_0110011;
      @1
         //Register File Read
         $rf_rd_en1 = $rs1_valid;
         $rf_rd_index1[4:0] = $rs1;  //m4+rf(@1, @1) takes input $rf_rd_index1[4:0] (which is index value of register of RISC-V)
                                     // and return its value as $rf_rd_data1 of 32 bit, which is the value stored in that register
         $rf_rd_en2 = $rs2_valid;
         $rf_rd_index2[4:0] = $rs2;   //m4+rf(@1, @1) takes input $rf_rd_index1[4:0] (which is index value of register of RISC-V)
                                     // and return its value as $rf_rd_data2 of 32 bit, which is the value stored in that register
         $src1_value[31:0] = $rf_rd_data1;
         $src2_value[31:0] = $rf_rd_data2;
      @1
         //ALU
         $result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx ;
      @1
         //Register File Write                  // $rd_valid = 1 when ISA have rd its instruction 
         $rf_wr_en1 = $rd_valid && $rd != 5'b0;  // if $rd_valid =0 or $rd =0 then then $rf_wr_en1 is 0
         $rf_wr_en = $valid && $rf_wr_en1;   //to stop the writing during invalid instruction
         $rf_wr_index[4:0] = $rd;                              // $rd=0(because x0 register of RISC-V always stores vale 32'b0 so can't be rewritten ) 
         $rf_wr_data[31:0] = $result;       // $result is coming from ALU and getting stored in $rf_wr_index[4:0] address of RISC-V register         
                                            // having value $rf_wr_data   
      @1
         //Branch Instructions
         $taken_branch = $is_beq ? ($src1_value == $src2_value):               //BEQ (Branch if Equal)
                         $is_bne ? ($src1_value != $src2_value):               //BNE (Branch if Not Equal)  
                         $is_blt ? (($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31])):    // BLT (Branch if Less Than)
                         $is_bge ? (($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31])):   //BGE (Branch if Greater Than or Equal)
                         $is_bltu ? ($src1_value < $src2_value):              //BLTU (Branch if Less Than Unsigned)
                         $is_bgeu ? ($src1_value >= $src2_value):             //BGEU (Branch if Greater Than or Equal Unsigned)
                                    1'b0;                 
         $br_tgt_pc[31:0] = $pc + $imm;
         $valid_taken_branch = ($valid && $taken_branch);   //To invalid the branch taken during invalid instruction or invalid clock
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = |cpu/xreg[10]>>5$value == (1+2+3+4+5+6+7+8+9);
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
      //m4+myth_fpga(@0)  // Uncomment to run on fpga

   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic. @4 would work for all labs.
\SV
   endmodule
```


### Lab to code complete ALU
<img width="551" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/12663035-d2ce-4edd-b6e1-3905be2446d9">

Next step here is to distribute the stages as we want in the pipeline.

For that we have to modify the RF like "m4+rf (@2,@3)" means register will read after @2 clock and write back after @3 clock. we have to set write back by >>2 because 1 stage is between both now.




## Solution to pipeline Hazards
### Lab for register file bypass to address Rd-After-Wr Hazard
#### Second solution of hazard: register file bypass
Assuming we have back to back instructions.

<img width="449" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b2ffc727-da43-4755-b929-88db4b5ba6c3">

Here red dotted line indicating the issue we currently have regardin register file writing that we don't have a time to write register file in previous instruction and read it in this instruction(read after write hazard). So we are going to remove that path and introduce a better solution. The problem we are facing when some instruction came and that want value of previous instruction which we are not able to write in RF due to next instruction strat perfoming. The solution is we will bypass the value (ALU output of previous instructio, that we want in next instruction)what we want to write in the register. we direct use previous value in the next input of ALU by bypassing from previous instruction. This is called register bypass.

For that we are adding this muxes and correcting this register file.

<img width="450" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/40a40d53-a65d-408f-a365-866281cb3dab">

To implemet it we have do this modification in code,

<img width="560" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/af7a682e-cd95-49e5-acd7-27a5956ddd75">



### Lab for branches to correct the branch target path
#### Task: Correct the branch traget path in branch type instruction
Our CPU is constantly updating the PC by one increment. and it will use this incremented PC value in the next instruction. If we find that we are taken the branch instruction then we have to correct the situation.

When we taken the branch instruction, we have to decode the instruction and then after calculation in register file we can get that branch istruction will be taken or not and after ALU, we can find the branch address and immediate value. so we can't avoid this 3 stages of cycle or we can't avoide this previous two dead instruction cycle here.

<img width="502" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/30447562-04ea-4838-8f03-bb735cdfe2ea">

One of the solution is branch prediction but we are not going to do it. we will suffer it by panelty of 2 dead cycles.

<img width="548" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/8bf3a9da-dbed-4789-92a7-4918f44baea0">

Here we can see these two dead cycles in waterfall diagram.

We have to implement branch logic like this,

<img width="527" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/72b3008e-c2ab-4be0-bfdf-9e5212dcc9ee">

To implement it we have to do some modification like this given below instructions.

<img width="505" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/6f57795e-d388-4edb-95ee-22d605156a44">



### Lab to complete instruction decode except Fence and Ecell and Ebreak
Till now we write the code to decode only subset instructions. Now lets decode other remaining instructions also.

Here we are not going to implement some instrcution from RV32I are Fence, Ecell and Ebreak.

Here we will treat all load instruction equally and will generate $is_load based on opcode only.(no required $func3 to generate $is_load operation). so we have to complete the code with other instructions also.

<img width="349" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/53de0571-59e0-4f33-a0a1-c74da0239b37">

TL verilog code for other instruction is given below,

```verilog
@1
         $instr[31:0] = $imem_rd_data[31:0]; 
               
          //Instructions type decode 
         $is_i_instr = $instr[6:2] ==? 5'b0000x || 
                       $instr[6:2] ==? 5'b001x0 || 
                       $instr[6:2] ==? 5'b11001 ;
         $is_r_instr = $instr[6:2] ==? 5'b011x0 || 
                       $instr[6:2] ==? 5'b01011 || 
                       $instr[6:2] ==? 5'b10100 ; 
         $is_s_instr = $instr[6:2] ==? 5'b0100x ;
         $is_b_instr = $instr[6:2] ==? 5'b11000 ;
         $is_j_instr = $instr[6:2] ==? 5'b11011 ;
         $is_u_instr = $instr[6:2] ==? 5'b0x101 ;
         
           //Instruction immediate decode
         $imm[31:0] = $is_i_instr ? {{21{$instr[31]}},$instr[30:20] }:
                      $is_s_instr ? {{21{$instr[31]}},$instr[30:25],$instr[11:8],$instr[7]} :
                      $is_b_instr ? {{20{$instr[31]}},$instr[7],$instr[30:25],$instr[11:8],1'b0} :
                      $is_u_instr ? {$instr[31], $instr[30:20],$instr[19:12],12'b0 }:
                      $is_j_instr ? {{12{$instr[31]}},$instr[19:12],$instr[20],$instr[30:21],1'b0} :
                      32'b0 ;
         $opcode[6:0] = $instr[6:0];

           //b. func7 decode

         $func7_valid = $is_r_instr ;
         ?$func7_valid
            $func7[6:0] = $instr[31:25];
         //c. rs2 decode

         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr ;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];

          //d. rs1 valid

         $rs1_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr ;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15] ;

          //e. func3 valid

         $func3_valid = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr ;
         ?$func3_valid
            $func3[2:0] = $instr[14:12] ;

         $rd_valid = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr ;
         ?$rd_valid
            $rd[4:0] = $instr[11:7];     
      
         $dec_bits[10:0] = {$func7[5], $func3, $opcode} ;
         $is_beq = $dec_bits ==? 11'bx_000_1100011 ;
         $is_bne = $dec_bits ==? 11'bx_001_1100011 ;
         $is_blt = $dec_bits ==? 11'bx_100_1100011 ;
         $is_bge = $dec_bits ==? 11'bx_101_1100011 ;           
         $is_bltu = $dec_bits ==? 11'bx_110_1100011 ;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011 ;  
         $is_addi = $dec_bits ==? 11'bx_000_0010011 ;
         $is_add = $dec_bits ==? 11'b0_000_0110011 ;
         
         $is_load = $dec_bits ==? 11'bx_xxx_0000011;
         
         $is_sb = $dec_bits ==? 11'bx_000_0100011;
         $is_sh = $dec_bits ==? 11'bx_001_0100011;
         $is_sw = $dec_bits ==? 11'bx_010_0100011;
         $is_slti = $dec_bits ==? 11'bx_010_0010011;
         $is_sltiu = $dec_bits ==? 11'bx_011_0010011;
         $is_xori = $dec_bits ==? 11'bx_100_0010011;
         $is_ori = $dec_bits ==? 11'bx_110_0010011;
         $is_andi = $dec_bits ==? 11'bx_111_0010011;
         $is_slli = $dec_bits ==? 11'b0_001_0010011;
         $is_srli = $dec_bits ==? 11'b0_101_0010011;
         $is_srai = $dec_bits ==? 11'b1_101_0010011;
         $is_sub = $dec_bits ==? 11'b1_000_0110011;
         $is_sll = $dec_bits ==? 11'b0_001_0110011;
         $is_slt = $dec_bits ==? 11'b0_010_0110011;
         $is_sltu = $dec_bits ==? 11'b0_011_0110011;
         $is_xor = $dec_bits ==? 11'b0_100_0110011;
         $is_srl = $dec_bits ==? 11'b0_101_0110011;
         $is_sra = $dec_bits ==? 11'b1_101_0110011;
         $is_or = $dec_bits ==? 11'b0_110_0110011;
         $is_and = $dec_bits ==? 11'b0_111_0110011;
         $is_lui = $dec_bits ==? 11'bx_xxx_0110111;
         $is_auipc = $dec_bits ==? 11'bx_xxx_0010111;
         $is_jal = $dec_bits ==? 11'bx_xxx_1101111;
         $is_jalr = $dec_bits ==? 11'bx_000_1100111;
         $is_jump = $is_jal || $is_jalr ;
         
         `BOGUS_USE($is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add) 
```



### Lab to code complete ALU
#### Task : write code for complete ALU

<img width="556" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/2238e9f1-bfe2-40f5-9fba-a4cc77bf4257">

These are the syntax for remaing opration that ALU will going to perform.

TL verilog code for complete ALU is given below,
```verilog
@3
     //Assigning aadi and add value to alu
         $sltu_rslt[31:0] = $src1_value < $src2_value ;
         $sltiu_rslt[31:0]  = $src1_value < $imm ;
         
         $result[31:0] =
              $is_addi ? $src1_value + $imm :
              $is_add ? $src1_value + $src2_value :
              $is_andi ? $src1_value & $imm :
              $is_ori  ? $src1_value | $imm :
              $is_xori ? $src1_value ^ $imm :
              $is_slli ? $src1_value << $imm[5:0] :  // shift left logic immediate
              $is_srli ? $src1_value >> $imm[5:0] : // shift right logic immediate
              $is_and ? $src1_value & $src2_value : 
              $is_or ? $src1_value | $src2_value :
              $is_xor ? $src1_value ^ $src2_value :
              $is_sub ? $src1_value - $src2_value :
              $is_sll ? $src1_value << $src2_value[4:0] :  // shift left logic
              $is_srl ? $src1_value >> $src2_value[4:0] :    // shift righ logic
              $is_sltu ? $src1_value < $src2_value :   //set less than unsigned
              $is_sltiu ? $src1_value < $imm :   //set less than unsigned immediate
              $is_lui ? {$imm[31:12], 12'b0} :  //load upper immediate
              $is_auipc ? $pc + $imm :    //add upper immediate at PC
              $is_jal ? $pc + 32'd4 :    //jump and link
              $is_jalr ? $pc + 32'd4 :  //jump and link register
              $is_srai ? {{32{$src1_value[31]}}, $src1_value} >> $imm[4:0] :  //shift right arithmatic immediate
              $is_slt ? ($src1_value[31] == $src2_value[31]) ? $sltu_rslt : {31'b0, $src1_value[31]} :  //set less than
              $is_slti ? ($src1_value[31] == $imm[31]) ? $sltiu_rslt : {31'b0, $src1_value[31]} :    //set less than immediate
              $is_sra ? {{32{$src1_value[31]}}, $src1_value} >> $src2_value[4:0] :  //shift right arithmatic
              $is_load || $is_s_instr ? $src1_value + $imm :
              32'bx ;
        //Register file write
         $rf_wr_en = $rd_valid && $rd != 5'b0 && $valid || >>2$valid_load ;
         $rf_wr_index[4:0] = >>2$valid_load ? >>2$rd : $rd ;
         $rf_wr_data[31:0] = >>2$valid_load ? >>2$ld_data : $result ;
```

## Load and Store Instructions and completing RISC-V CPU
### Intriduction to load and store instruction and lab to Redirect loads
Let's implement the load and store instruction. For that we need Data memory. In RISC_V, There are five diffrent types of LOAD instruction (LW,LH,LB,LHU,LBU). These instructions support both signed and unsigned loads of different width of data. (Because of signed and unsigned, extension of upper bit gets affected). similar for store(Sw,SH,SB).

<img width="560" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/c850f8a4-2a96-4855-a39a-aa562791a147">

Here in rd, value stored in takem from data memory and address of that memory is calculated from (imm and rs1).

In the diagram, we can see that after data memory we can take the load and store data. but again we can load and store the data after two cycle from when we calculate the load and store address. So, we can't write the register file with load data. So, we have an another hazard here and we have to solve this hazard.

Let's look at waterfall diagram here,

<img width="551" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/b327ad68-4d1f-4930-9c6c-0ff16cb7bc94">

Here what happed is, in 3rd cycle, at execution time, load address is generated and after 2 cycle it will be written in data memory to RF. so if "rt" instruction is running in 5th cycle then we can not write two data at a same time in RF. so we have to pass this 4th and 5th instruction after the data is loaded in Data memory. for that we have to do the same thing what we have done in branch instruction. we will unvalid these 4th and 5th cycle at that time and again we will perform the 4th and 5th instruction at 6th and 7th cycle. basically at 4th cycle we will get the addess of data memory and data, and at 5th cycle we will load this data in to data memory  and at 6th cycle we will write these data into RF. if we don't unvalid 4th and 5th operation then at 7th cycle writing operation of 5th instruction will collaps with writing opration of load data.

it's looks like this in water fall diagram.

<img width="497" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/226bf97e-a597-4508-8652-6d635ccddd16">

For that we have to clear $valid signal in the shadow of the load like branch. and we have to select PC from 3 cycle ago to reperform this unvalid cycle's instructions.

<img width="520" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/fd437466-d793-4407-873d-5c54f8c128d2">



### Lab to load data from memory to register file
Till now we unvalid the two operations after the load operation. now we have to load the data to data memory and then we have to write the data into RF file. for that First we have to calculate the data memory address (and data if we are performing store operation) and then we will store or load data from data memory and then we will write it back into RF.

<img width="521" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/0d5c43c3-85df-42bd-8255-8c5ad2953bfd">

For that we have to follow the step given below,

<img width="506" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/8bcf11e9-4d45-4c43-bac7-9316f0f1cd02">

In first step, $is_load and $is_s_instr are the instruction where we have to calculate the address. In second step we have to add one RF_Wr mux to select the $ld_data when !$valid is available. (means during unvalid cycles). In third step we have to enable the RF_Wr for $ld_data after 2 cycles from $load came.


### Lab to instantiate data memory to register file
Now it's time to instantiate the data memory by uncommenting [m4+dmem (@4)].

And next task is to connect all signals that data memory required like $reset,$dmem_wr_en,$dmem_rd_en,$dmem_wr_add,$dmem_wr_data,$dmem_rd_index[5:0] and $dmem_rd_data.

<img width="263" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/1cd8b016-4106-4051-99fc-d006bd9ffb1c">

We can connect the interface signals using address bits[5:2] (because only 16 entries are possible)to perform load and store when $valid is available.


### Lab for add and stores and load to the test program
To test the program, we have to add two instructions at the end of Assebly language program.

<img width="171" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/0ddb96b6-483d-48e9-a9be-5d678ccc0ee8">

Here 100 is binary number. because of "sw , r0, r10, 100" we are going to store the value of R0 into value of [deta memory addree= value of R10+4]. and the same value it will take from memory and load into the register R15. so it is used as a test bench of our code. As we use passing condition where we use xreg[10], now we have to update it as xreg[15]. 

So passing condition is like ```*passed = |cpu/xreg[15]>>5$value == (1+2+3+4+5+6+7+8+9);
                                *failed = 1'b0;
                             ```

### Lab to add control logic for jump instruction
Now only one instruction remaining to add into RISC_V CPU core and this instruction is JUMP. basically jumps are unconditional branches.

There are two types of jump instruction. (1)JAL(jump and link) : jump to an address=(PC+imm)  and (2)JALR(jump and link to register): jump to address=src1+imm.

To implement it we have to follow these steps given below,

<img width="545" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/79888d97-4ab1-4806-9caa-ab519fb49173">

So In architecture block jump is shown by red line,

<img width="517" alt="image" src="https://github.com/piyushkandoriya/RISC-V-based-MYTH/assets/123488595/a1c21b59-f9a1-473c-9b5d-cd2d6d613977">

### Final 4 stage RISC-V pipelined architecture

TL Verilog code for FINAL 4 STAGE RISC-V ARCHITECTURE is given below,


```verilog

```

###  Wrap up
In this workshop, i got knowlage about RISC-V CPU, it's architecture and it's digital level design. Also learn how to use tool like mackerchip and the TL verilog (transational level verilog).

# References
https://github.com/RISCV-MYTH-WORKSHOP/RISC-V-CPU-Core-using-TL-Verilog

https://github.com/stevehoover/RISC-V_MYTH_Workshop

https://drive.google.com/file/d/1ZcjLzg-53It4CO3jDLofiUPZJ485JZ_g/view

https://drive.google.com/file/d/1tqvXmFru31-tezDX30jTNJoLcQk308UM/view

https://github.com/shivanishah269/risc-v-core

https://myth.makerchip.com/sandbox?code_url=https:%2F%2Fraw.githubusercontent.com%2Fstevehoover%2FRISC-V_MYTH_Workshop%2Fmaster%2Freference_solutions.tlv#

https://github.com/TL-X-org/TL-V_Projects"

# Acknowledgement
I would like to express my special thanks of gratitude to [Mr. kunal ghosh](https://github.com/kunalg123) (co.-founder of VLSIsystem design (VSD) corp.pvt.ltd.) and [Mr. Steve Hoover](https://github.com/stevehoover)  (Founder, Redwood EDA) for their guidence and temendous presenting this workshop on RISC-V based MYTH. The Workshop was excellent and well designed. This workshop taught me a lot of new things about the RISC-V architecture and its digital level disign, TL verilog, Mackerchip platform and many more.

# Inquiries
Contact me on a [linkedin](https://www.linkedin.com/in/piyush-kandoriya-b96675248)
