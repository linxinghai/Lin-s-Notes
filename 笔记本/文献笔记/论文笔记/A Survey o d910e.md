# A Survey on FPGA Virtualization

Authors' affliation: university of manchester
Fields: datacenter, fpga, overlay, virtualization
Priority: high
Read: Yes
Venue: FPL
Year: 2018

## ☘️Paper in 3 Sentences

1. Three Levels of FPGA virtualization
    1. Resources level
    2. Node level
    3. Multi-node level
2. Good summary on FPGA virtualization: types, pros & cons, and example work.

## ☘️Impressions

![A%20Survey%20o%20d910e/Untitled.png](笔记本/文献笔记/论文笔记/A%20Survey%20o%20d910e/Untitled.png)

## ☘️Top 3 Quotes

- 

## ☘️Notes

### Main objectives of FPGA virtualization

- Multi-tenancy: Ability to serve multiple different users using the same FPGA fabric.
- Resource Management: Providing an abstraction/driver layer to the FPGA fabric and means of scheduling tasks to the FPGA as well as monitoring its resource usage.
- Flexibility: Ability to support a wide range of acceleration workload i.e. from custom accelerators to framework specific accelerators designed in a High-Level Language (HLL) or a Domain Specific Language (DSL).
- Isolation: Providing the illusion of being a sole user of the FPGA resources for better security, fewer dependencies and correctness of the program execution.
- Scalability: The system/application can scale to multiple different FPGAs or can support multiple different users at relatively low overhead.
- Performance: The impact of virtualization should be minimal on performance achievable and FPGA resources usable by the user application.
- Security: Ensuring information of other tenants is not leaked and for safekeeping the infrastructure from malicious users.
- Resilience: Ability to keep the system/service running despite failures.
- Programmer’s productivity: Improving the time to market and reducing the complexity of deploying a design to an FPGA from its software description.

### 🍁Main diffucilities of HW virtualization

<aside>
💡 Due to one fundamental difference between CPU/GPUs and FPGAs i.e. applications are hardware circuits rather than a set of commands in assembly.

</aside>

- a very high context switch penalty,
- space-time sharing rather than just time,
- different development tools,
- high development time and high heterogeneity in the system as each accelerator represents a distinct hardware module

---

### 🍁Overlay

<aside>
💡 Overlays provide another level of programmability that is implemented on top of the low-level FPGA resources.

</aside>

Author classified overlay as a 'Resource-level' virtualization, to provide architecture abstraction.

![A%20Survey%20o%20d910e/Untitled%201.png](笔记本/文献笔记/论文笔记/A%20Survey%20o%20d910e/Untitled%201.png)

### Types of coarse-grained FPGA overlays

- soft-core processors, either from academia [24] or from industrial vendors [25], [26],
- vector processors [27]–[31],
- connected arrays of processing elements (PEs) [9], [32]–[35] in which programmable PEs and interconnects are provided
    - i.e. CGRA

<aside>
💡 Overall, the extra level of programmability through an overlay comes at a substantial cost that needs to be justified.

</aside>

Potentially benefits:

- overlay abstraction allows domain experts (who are not FPGA experts) to benefit from FPGAs
- Better for situations that require rapidly changing functionality (at a speed which cannot be met using partial reconfiguration)
    - e.g. VectorBlox
    

---

## URL