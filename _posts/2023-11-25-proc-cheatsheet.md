---
layout: post
title:  "/proc Cheatsheet"
date:   2023-11-25 06:00:00 +0700
categories: computer
---
### /proc/cpuinfo
```
processor       : 0 # processor id
vendor_id       : GenuineIntel 
cpu family      : 6 # 6th generation of the Intel Core family
model           : 154 # a specific model within the 6th generation Intel Core family
model name      : 12th Gen Intel(R) Core(TM) i9-12900H
stepping        : 3 # a specific revision or stepping of the processor
microcode       : 0xffffffff # the version of microcode that is loaded onto the CPU, a layer of software that sits between the operating system and the hardware, and it is used to provide updates and corrections to the processor's instruction set
cpu MHz         : 2918.399 # current clock speed
cache size      : 24576 KB # combined size of all cache levels on the CPU
physical id     : 0 # the physical package or socket that a particular CPU core belongs to in a multiprocessor system. single-socket systems, the "physical id" for all CPU cores will typically be 0
siblings        : 20 # total number of logical processors (or threads) in a physical processor package
core id         : 0 # identifier of the core within a physical processor package
cpu cores       : 10 # number of physical CPU cores present in a processor
apicid          : 0 # (Advanced Programmable Interrupt Controller ID) manages interrupts and is responsible for distributing interrupts to the appropriate CPU cores
initial apicid  : 0 # initial
fpu             : yes # indicates whether the CPU has a Floating Point Unit (FPU)
fpu_exception   : yes # indicates whether the CPU supports trapping and handling of Floating-Point Unit (FPU) exceptions
cpuid level     : 28 # highest level of the CPUID instruction supported by the processor. The CPUID instruction is an x86 instruction that allows software to query information about the processor's capabilities and features
wp              : yes # indicates whether the CPU supports write-protect (WP) for pages. When a page in memory is marked as write-protected, attempts to write to that page will result in a hardware exception or fault
flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl xtopology tsc_reliable nonstop_tsc cpuid pni pclmulqdq vmx ssse3 fma cx16 pcid sse4_1 sse4_2 x2apic movbe popcnt tsc_deadline_timer aes xsave avx f16c rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single ssbd ibrs ibpb stibp ibrs_enhanced tpr_shadow vnmi ept vpid ept_ad fsgsbase tsc_adjust bmi1 avx2 smep bmi2 erms invpcid rdseed adx smap clflushopt clwb sha_ni xsaveopt xsavec xgetbv1 xsaves umip waitpkg gfni vaes vpclmulqdq rdpid movdiri movdir64b fsrm serialize flush_l1d arch_capabilities # flags or features supported by the CPU
vmx flags       : vnmi invvpid ept_x_only ept_ad ept_1gb tsc_offset vtpr ept vpid unrestricted_guest ept_mode_based_exec tsc_scaling usr_wait_pause # information about additional features related to Intel Virtualization Technology (VT-x)
bugs            : spectre_v1 spectre_v2 spec_store_bypass swapgs # information about known errata or issues associated with the CPU
bogomips        : 5836.79 # an estimate of the processor speed in million instructions per second (MIPS)
clflush size    : 64 # indicates the cache line size in bytes for the CPU's cache architecture
cache_alignment : 64 # there isn't a specific field named "cache_alignment" in the standard /proc/cpuinfo output on Linux systems
address sizes   : 46 bits physical, 48 bits virtual # information about the supported virtual and physical address sizes of the processor
power management: # information about the power management features supported by the CPU
```

### /proc/meminfo
```
MemTotal:       16231340 kB
MemFree:        12375448 kB
MemAvailable:   15105564 kB
Buffers:          254020 kB
Cached:          2508568 kB
SwapCached:            0 kB
Active:          1288420 kB
Inactive:        1926016 kB
Active(anon):        308 kB
Inactive(anon):   451864 kB
Active(file):    1288112 kB
Inactive(file):  1474152 kB
Unevictable:           0 kB
Mlocked:               0 kB
SwapTotal:       4194304 kB
SwapFree:        4194304 kB
Dirty:                84 kB
Writeback:             0 kB
AnonPages:        447456 kB
Mapped:            85212 kB
Shmem:               320 kB
KReclaimable:     300848 kB
Slab:             365336 kB
SReclaimable:     300848 kB
SUnreclaim:        64488 kB
KernelStack:        5536 kB
PageTables:         9448 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:    12309972 kB
Committed_AS:    1011588 kB
VmallocTotal:   34359738367 kB
VmallocUsed:       26016 kB
VmallocChunk:          0 kB
Percpu:             7872 kB
AnonHugePages:    129024 kB
ShmemHugePages:        0 kB
ShmemPmdMapped:        0 kB
FileHugePages:         0 kB
FilePmdMapped:         0 kB
HugePages_Total:       0
HugePages_Free:        0
HugePages_Rsvd:        0
HugePages_Surp:        0
Hugepagesize:       2048 kB
Hugetlb:               0 kB
DirectMap4k:      121856 kB
DirectMap2M:     7057408 kB
DirectMap1G:    17825792 kB
```