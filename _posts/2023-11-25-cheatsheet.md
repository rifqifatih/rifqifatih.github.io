---
layout: post
title:  "Cheatsheet"
date:   2023-11-25 06:00:00 +0700
categories: computer
---
### /proc/cpuinfo
```
processor       : 0 # Processor id
vendor_id       : GenuineIntel 
cpu family      : 6 # 6th generation of the Intel Core family
model           : 154 # A specific model within the 6th generation Intel Core family
model name      : 12th Gen Intel(R) Core(TM) i9-12900H
stepping        : 3 # A specific revision or stepping of the processor
microcode       : 0xffffffff # The version of microcode that is loaded onto the CPU, a layer of software that sits between the operating system and the hardware, and it is used to provide updates and corrections to the processor's instruction set
cpu MHz         : 2918.399 # Current clock speed
cache size      : 24576 KB # Combined size of all cache levels on the CPU
physical id     : 0 # The physical package or socket that a particular CPU core belongs to in a multiprocessor system. single-socket systems, the "physical id" for all CPU cores will typically be 0
siblings        : 20 # Total number of logical processors (or threads) in a physical processor package
core id         : 0 # Identifier of the core within a physical processor package
cpu cores       : 10 # Number of physical CPU cores present in a processor
apicid          : 0 # (Advanced Programmable Interrupt Controller ID) manages interrupts and is responsible for distributing interrupts to the appropriate CPU cores
initial apicid  : 0 # Initial
fpu             : yes # Indicates whether the CPU has a Floating Point Unit (FPU)
fpu_exception   : yes # Indicates whether the CPU supports trapping and handling of Floating-Point Unit (FPU) exceptions
cpuid level     : 28 # Highest level of the CPUID instruction supported by the processor. The CPUID instruction is an x86 instruction that allows software to query information about the processor's capabilities and features
wp              : yes # Indicates whether the CPU supports write-protect (WP) for pages. When a page in memory is marked as write-protected, attempts to write to that page will result in a hardware exception or fault
flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl xtopology tsc_reliable nonstop_tsc cpuid pni pclmulqdq vmx ssse3 fma cx16 pcid sse4_1 sse4_2 x2apic movbe popcnt tsc_deadline_timer aes xsave avx f16c rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single ssbd ibrs ibpb stibp ibrs_enhanced tpr_shadow vnmi ept vpid ept_ad fsgsbase tsc_adjust bmi1 avx2 smep bmi2 erms invpcid rdseed adx smap clflushopt clwb sha_ni xsaveopt xsavec xgetbv1 xsaves umip waitpkg gfni vaes vpclmulqdq rdpid movdiri movdir64b fsrm serialize flush_l1d arch_capabilities # flags or features supported by the CPU
vmx flags       : vnmi invvpid ept_x_only ept_ad ept_1gb tsc_offset vtpr ept vpid unrestricted_guest ept_mode_based_exec tsc_scaling usr_wait_pause # Information about additional features related to Intel Virtualization Technology (VT-x)
bugs            : spectre_v1 spectre_v2 spec_store_bypass swapgs # Information about known errata or issues associated with the CPU
bogomips        : 5836.79 # an estimate of the processor speed in million instructions per second (MIPS)
clflush size    : 64 # Indicates the cache line size in bytes for the CPU's cache architecture
cache_alignment : 64 # There isn't a specific field named "cache_alignment" in the standard /proc/cpuinfo output on Linux systems
address sizes   : 46 bits physical, 48 bits virtual # Information about the supported virtual and physical address sizes of the processor
power management: # Information about the power management features supported by the CPU
```

### /proc/meminfo
```
MemTotal:       16231340 kB # Total usable RAM in kilobytes
MemFree:        12375448 kB # The sum of Free, LowFree, and HighFree. Represents the total amount of free and unused memory
MemAvailable:   15105564 kB # An estimate of how much memory is available for starting new applications, without swapping
Buffers:          254020 kB # Memory used by kernel buffers in kilobytes
Cached:          2508568 kB # Memory used by the page cache and slabs (Cached and SReclaimable)
SwapCached:            0 kB # Memory that was once swapped out and is now back in RAM but still marked as swapped. It is not actively used
Active:          1288420 kB # Memory currently in use or recently used. It includes both anonymous and file-backed memory. Active(anon) + Active(file)
Inactive:        1926016 kB # Memory that is marked as not in use. Inactive(anon) + Inactive(file)
Active(anon):        308 kB # "Anonymous memory" refers to memory that is not associated with any specific file or device
Inactive(anon):   451864 kB # Memory that was allocated to processes but is no longer in use
Active(file):    1288112 kB # "File-backed memory" refers to memory that is associated with specific files on the system. This memory is often used as a cache for file data to speed up access times
Inactive(file):  1474152 kB # Memory that was allocated to files but is no longer in use
Unevictable:           0 kB # Memory that cannot be swapped out (e.g., locked by the kernel or reserved for hardware)
Mlocked:               0 kB # Memory that is locked in physical memory, preventing it from being swapped
SwapTotal:       4194304 kB # Total amount of swap space in kilobytes
SwapFree:        4194304 kB # Indicates the portion of the total swap space (as indicated by "SwapTotal") that is available for use
Dirty:                84 kB # Amount of memory that contains data modified by user processes but has not been written to the swap space or filesystem on disk. MMU assists the operating system in marking pages as "dirty" when write operations occur
Writeback:             0 kB # Indicates the amount of data that is in the process of being asynchronously written back to disk. This includes data that has been modified in memory (dirty pages) and is scheduled for flushing to persistent storage
AnonPages:        447456 kB # Active(anon) + Inactive(anon). If there's a discrepancy, it could be due to changes in the system's memory state between the time of reading the values
Mapped:            85212 kB # Total amount of file-backed memory that is mapped into userspace page tables. This includes memory-mapped files and devices
Shmem:               320 kB # Shared memory is a form of inter-process communication (IPC) that allows multiple processes to share a region of memory. Processes can read from and write to this shared memory region, enabling efficient communication between them
KReclaimable:     300848 kB # Part of the kernel's own structures which can be reclaimed if necessary
Slab:             365336 kB # Memory allocated by the kernel for caches of objects. The slab allocator is a memory allocation mechanism employed by the Linux kernel to efficiently manage small, frequently allocated objects, often associated with data structures and caches
SReclaimable:     300848 kB # Represents the part of the "Slab" memory that can be reclaimed by the kernel
SUnreclaim:        64488 kB # Amount of memory within the slab allocator that is not currently reclaimable by the kernel
KernelStack:        5536 kB # Indicates the total amount of memory used by kernel stacks
PageTables:         9448 kB # Indicates the total amount of memory used by the page tables
NFS_Unstable:          0 kB # NFS pages are considered unstable when they have been modified but have not yet been written back to the NFS server. This situation can occur when a process modifies a file on an NFS-mounted file system, and the changes are cached locally. The "NFS_Unstable" field reflects the memory used by these modified but not yet stable pages
Bounce:                0 kB # There isn't a standard field named "Bounce" in the /proc/meminfo file on Linux systems. It might be related to a specific kernel feature, module, or system configuration that wasn't prevalent or widely known up to my last update
WritebackTmp:          0 kB # 
CommitLimit:    12309972 kB # Estimate of how much RAM and swap space (virtual memory) the system can commit for future allocation requests without running out of memory. The "CommitLimit" is a broader metric that includes both RAM and swap space as oppose to only physical RAM in MemFree
Committed_AS:    1011588 kB # Total amount of memory (both physical RAM and swap space) that has been committed by the system for its internal use
VmallocTotal:   34359738367 kB # Total amount of virtual memory allocated for vmalloc (virtual memory allocation) areas in the kernel. This includes the total size of the virtual memory space that has been reserved by the kernel for various purposes, such as dynamic kernel data structures and other kernel-related allocations
VmallocUsed:       26016 kB # Amount of virtual memory that is currently in use within the vmalloc (virtual memory allocation) space of the kernel
VmallocChunk:          0 kB # 
Percpu:             7872 kB # 
AnonHugePages:    129024 kB # Amount of memory used for anonymous transparent huge pages. Huge pages are larger-sized memory pages that can improve performance by reducing the overhead of managing a large number of smaller pages. Transparent Huge Pages (THP) is a feature that automatically manages the use of huge pages by the kernel
ShmemHugePages:        0 kB # Amount of memory, in kilobytes, used for transparent huge pages backed by shared memory (shmem)
ShmemPmdMapped:        0 kB # 
FileHugePages:         0 kB # 
FilePmdMapped:         0 kB # 
HugePages_Total:       0 # Total number of huge pages that are currently available in the system
HugePages_Free:        0 # Number of huge pages that are currently not in use and are available for allocation
HugePages_Rsvd:        0 # Number of huge pages that are reserved for future use but are not currently in use
HugePages_Surp:        0 # Number of surplus (extra) huge pages that are not expected by the system and are therefore not reserved
Hugepagesize:       2048 kB # Specifies the size of each huge page in kilobytes
Hugetlb:               0 kB # 
DirectMap4k:      121856 kB # Amount of memory that is directly mapped into the kernel's address space with a page size of 4 kilobytes. This mapping is often associated with the low 4 GB of physical memory
DirectMap2M:     7057408 kB # Amount of memory that is directly mapped into the kernel's address space with a larger page size of 2 megabytes. This mapping is often associated with higher regions of physical memory
DirectMap1G:    17825792 kB # 
```