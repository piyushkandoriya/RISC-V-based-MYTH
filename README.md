# **RISC-V-based-MYTH**
# Contents 
 <div class="toc">
  <ul>
    <li><a href="#header-1">Day 1 - Introduction to RISC-V ISA and GNU compiler toolchain </a></li>
	<ul>
        <li><a href="#header-1_1"> Introduction to RISC-V basic keyword </a></li>
      </ul>
      <ul>
        <li><a href="#header-1_2"> Labwork for RISC_V software toolchain </a></li>
      </ul>
	<ul>
        <li><a href="#header-1_3">Integer number representation</a></li>
      </ul>
   </div>
     
<div class="toc">
  <ul>
    <li><a href="#header-2">Day 2 - Good floor planning considerations</a></li>
	<ul>
        <li><a href="#header-2_1"> Chip Floor planning consideration</a></li>
      </ul>
      <ul>
        <li><a href="#header-2_2">Library building and Placement</a></li>
      </ul>
	<ul>
        <li><a href="#header-2_3">Cell design and characterization flows</a></li>
      </ul>
	  <ul>
        <li><a href="#header-2_4">General timing characterization parameters</a></li>
        </ul>
</div>
  
  <div class="toc">
  <ul>
    <li><a href="#header-3">Day 3 - Design library cell using Magic Layout and ngspice characterization</a></li>
	<ul>
        <li><a href="#header-3_1"> Labs for CMOS inverter ngspice simulations</a></li>
      </ul>
      <ul>
        <li><a href="#header-3_2">Inception of layout ̂A CMOS faabrication process </a></li>
      </ul>
	<ul>
        <li><a href="#header-3_3">Sky130 Tech File Labs</a></li>
           </ul>
   </div>
	  
<div class="toc">
  <ul>
    <li><a href="#header-4">Day 4 - Pre-layout timing analysis and importance of good clock tree</a></li>
	<ul>
        <li><a href="#header-4_1">Timing modeling using delay tables</a></li>
      </ul>
      <ul>
        <li><a href="#header-4_2">Timing analysis with ideal clocks using openSTA</a></li>
      </ul>
	<ul>
        <li><a href="#header-4_3">Clock tree synthesis TritonCTS and signal integrity</a></li>
      </ul>
	  <ul>
   <li><a href="#header-4_4">Timing analysis with real clock using openSTA</a></li>
      </ul>
</div>
	
<div class="toc">
  <ul>
    <li><a href="#header-5">Day 5 -Final step for RTL2GDS using tritinRoute and openSTA</a></li>
	<ul>
        <li><a href="#header-5_1">Routing and design rule check (DRC)</a></li>
      </ul>
      <ul>
        <li><a href="#header-5_2">Power Distribution Network and routing</a></li>
      </ul>
	<ul>
        <li><a href="#header-5_3">TritonRoute Features</a></li>
        </ul>
</div>

<div class="toc">
  <ul>
    <li><a href="#header-6">All commands to run the openlane flow</a></li>
  </ul>
</div>

	
<div class="toc">
  <ul>
    <li><a href="#header-7">References</a></li>
  </ul>
</div>

<div class="toc">
  <ul>
    <li><a href="#header-8">Acknowledgement</a></li>
  </ul>
</div>

# <h1 id="header-1">Day 1 -Inception of open-source EDA, OpenLANE and sky130 PDK</h1>	 
## <h1 id="header-1_1"> How to talk to computers?</h1>
  
