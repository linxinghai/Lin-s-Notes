# Time-multiplexed FPGA Overlay architectures: A survey

Authors: Xiangwei Li
Authors' affliation: university of sydeny
Fields: fpga, overlay, virtualization
Priority: high
Read: Yes
Venue: ACM Trans on Design Automation of Electronic Systems
Year: 2019

## ☘️Paper in 3 Sentences

---

1. A survey on FPGA [overlay](https://www.notion.so/f812453230244c04a4a836e9b7b258c4), specifically on 'time-multiplexed' type of overlay, which allow it to change its behaviour cycle by cycle during hte comput kernel execution, thus allowing for better usage of FPGA resources. 
2. Most successful TM based FPGA overlay are implemented based on processors, hence lots of research are focus on developing differnet types of processors, which can be classified in 4 types.
3. CGRA-based overlay can improve design productivity, but suffer from lower speed and higher fpga resource utilization than RTL-based or HLS-based FPGA designs.

## ☘️Impressions

## ☘️Top 3 Quotes

---

- Benefit of Overlay Time-multiplexing the overlay allows it to change its behavior with a cycle-by-cycle execution of the application kernel, thus allowing better sharing of the limited FPGA hardware resource.
- Overlay Fundamental Overlay architectures promise to tackle the “programmability wall” of FPGAs by avoiding the tedious fine-grained placement and routing process.
- Cost of Overlay They generally come at the cost of a lower performance with significantly more FPGA resource used than for an equivalent design mapped directly to FPGA

## ☘️Notes

---

### 🍁Two types of overlay:

1. Spatially configured (SC): FU(functional unit) has a single fixed functionality at run-time
2. Time-multiplexed (TM): FU changes its operation on a cycle-by-cycle basis.
3. 

### 🍁Three types of soft processors:

1. single-issue processor
    - e.g. MicroBlaze, NiosII, OpenRISC
2. multi-issue processor
    - multi-issue or superscalar single processor
    - e.g. LEON3
    - requries significnat hardware complexity to dynamically extract the instruction parallesim - fpga implementation results in very high hw cost
3. multithreaded processor
    - improve area-efficiency, instruction-per-cycle (IPC) count
    - still based on NIOS or MicroBlaze core
    

### 🍁Main disadvantages of SVP

1. the scalability of SVPs is limited by the number of vector lanes, which is determined by the hardware resources on the FPGA. 
2. While increasing the number of vector lanes signifcantly increases the throughput, it also leads to clock frequency degradation. 
3. Compiler support for these processors is still at the primary stage as the repository of common operations and data types needs to be further improved

## ☘️Overall

### 🍁Benefits of Processor-based Overlay

- processor-based overlays have the advantage of well understood ISAs and easily accessible compilation tool chains making application development much easier for non-hardware designers
- processor-based overlays using parallel processing techniques, such as multi-issue, multithreading, VLIW, and vector processing, have been developed and shown to improve overlay performance

### 🍁Cost of Processor-based Overlay

- suﬀer from similar problems to processors implemented directly in silicon, such as being complex with signifcant resource utilization and power consumption, which tends to negate some of the designer productivity advantages (such as their software programmability).

### 🍁Benefits of CGRA-based Overlay

- better tailored towards area-efcient higher speed processing than processor-based overlays
- Particularly targeted towards the acceleration of comput intensive loops

### 🍁Cost of CGRA-based Overlay

- suﬀer from a lower speed and higher FPGA resource utilization than direct HDLor HLS-based application implementation on FPGA

## ☘️Future Directions

## ☘️URL