# Cmpe283-Virtualization-Assignment-1

Team Members: 
1)Pramatha Nadig
 2)Rishikesh Andhare
Effort Distribution
Pramatha Nadig
•	Created the VM on Google Cloud Platform with the configurations as per the requirement in Assignment-1
•	MSR COMPLETED-
o	IA32_VMX_PINBASED_CTLS  0x481
o	IA32_VMX_ENTRY_CTLS   0x484
o	IA32_VMX_EXIT_CTLS     0x483

Rishikesh Andhare
•	Created the VM on Google Cloud Platform with the configurations as per the requirement in Assignment-1
•	MSR COMPLETED- 
o	IA32_VMX_PROCBASED_CTLS
o	IA32_VMX_PROCBASED_CTLS2
o	IA32_VMX_PROCBASED_CTLS3

Steps for completing the assignment:
i.	Create a VM in Google Cloud Platform under the compute engine section with nested virtualization enabled.
ii.	Selected “Intel Haswell” as CPU platform with architecture x86/64.
iii.	Run the VM using SSH
iv.	In the VM terminal we have created a cmpe283.c file which is a source file ,containing the code for Reading Capabilities of MSRs.
v.	Created a Makefile 
vi.	 For installing make tool and gcc compiler on VM
a.	Run sudo apt install gcc make
vii.	There are 6 MSR’s in the assignment for which we have to detect the capabilities on our GCP VM.
a) IA32_VMX_PINBASED_CTLS 0x481
b) IA32_VMX_PROCBASED_CTLS 0x482
c) IA32_VMX_PROCBASED_CTLS2 0x48B
d) IA32_VMX_EXIT_CTLS 0x483
e) IA32_VMX_ENTRY_CTLS 0x484
f) IA32_VMX_PROCBASED_CTLS3 0X92
viii.	Run under the same directory with MakeFile and cmpe283.c file in terminal using the command
make
ix.	Files generated are:-
 
x.	Run the command sudo insmod cmpe283.ko to run the source file
xi.	Run sudo dmesg to detect the capabilities on the VM for the MSR’
xii.	Upon running these command we will be able to see the message outputs for the MSR’s pin-based, primary, secondary 
and tertiary procbased, exit and entry  control on terminal.

OUTPUTS:-

IA32_VMX_PINBASED_CTLS 0x481  (output )
[11978.813834] Pinbased Controls MSR: 0x3f00000016
[11978.818486]   External Interrupt Exiting: Can set=Yes, Can clear=Yes
[11978.824957]   NMI Exiting: Can set=Yes, Can clear=Yes
[11978.830134]   Virtual NMIs: Can set=Yes, Can clear=Yes
[11978.835387]   Activate VMX Preemption Timer: Can set=No, Can clear=Yes
[11978.842067]   Process Posted Interrupts: Can set=No, Can clear=Yes


IA32_VMX_PROCBASED_CTLS 0x482(output )
[11978.848391] Processor based Controls MSR: 0xf7b9fffe0401e172
[11978.854258]   Interrupt Window Exiting: Can set=Yes, Can clear=Yes
[11978.860559]   Use TSC Offsetting: Can set=Yes, Can clear=Yes
[11978.866338]   HLT Exiting: Can set=Yes, Can clear=Yes
[11978.871566]   INVLPG Exiting: Can set=Yes, Can clear=Yes
[11978.877186]   MWAIT Exiting: Can set=Yes, Can clear=Yes
[11978.882545]   RDPMC Exiting: Can set=Yes, Can clear=Yes
[11978.887889]   RDTSC Exiting: Can set=Yes, Can clear=Yes
[11978.893358]   CR3 Load Exiting: Can set=Yes, Can clear=No
[11978.899102]   CR3 Store Exiting: Can set=Yes, Can clear=No
[11978.904703]   Activate Tertiary Controls: Can set=No, Can clear=Yes
[11978.911094]   CR8 Load Exiting: Can set=Yes, Can clear=Yes
[11978.916693]   CR8 Store Exiting: Can set=Yes, Can clear=Yes
[11978.922378]   Use TPR Shadow: Can set=Yes, Can clear=Yes
[11978.927806]   NMI Window Exiting: Can set=No, Can clear=Yes
[11978.933490]   MOV-DR Exiting: Can set=Yes, Can clear=Yes
[11978.939012]   Unconditional I/O Exiting: Can set=Yes, Can clear=Yes
[11978.945432]   Use I/O Bitmaps: Can set=Yes, Can clear=Yes
[11978.951128]   Monitor Trap Flag: Can set=No, Can clear=Yes
[11978.956741]   Use MSR Bitmaps: Can set=Yes, Can clear=Yes
[11978.962424]   MONITOR Exiting: Can set=Yes, Can clear=Yes
[11978.968027]   PAUSE Exiting: Can set=Yes, Can clear=Yes
[11978.973478]   Activate Secondary Controls: Can set=Yes, Can clear=Yes

IA32_VMX_PROCBASED_CTLS2 0x48B(output )

[11978.980273] Processor based Secondary Controls MSR: 0x51ff00000000
[11978.986583]   Virtualize APIC accesses: Can set=Yes, Can clear=Yes
[11978.993095]   Enable EPT: Can set=Yes, Can clear=Yes
[11978.998268]   Descriptor Table Exiting: Can set=Yes, Can clear=Yes
[11979.004562]   Enable RDTSCP: Can set=Yes, Can clear=Yes
[11979.009913]   Virtualize x2APIC Mode: Can set=Yes, Can clear=Yes
[11979.016032]   Enable VPID: Can set=Yes, Can clear=Yes
[11979.021215]   WBINVD Exiting: Can set=Yes, Can clear=Yes
[11979.026649]   Unrestricted Guest: Can set=Yes, Can clear=Yes
[11979.032510]   APIC-register Virtualization: Can set=Yes, Can clear=Yes
[11979.039150]   Virtual-interrupt Delivery: Can set=No, Can clear=Yes
[11979.045531]   PAUSE-loop Exiting: Can set=No, Can clear=Yes
[11979.051239]   RDRAND exiting: Can set=No, Can clear=Yes
[11979.056678]   Enable INVPCID: Can set=Yes, Can clear=Yes
[11979.062290]   Enable VM Functions: Can set=No, Can clear=Yes
[11979.068068]   VMCS Shadowing: Can set=Yes, Can clear=Yes
[11979.073496]   Enable ENCLS Exiting: Can set=No, Can clear=Yes
[11979.079356]   RDSEED Exiting: Can set=No, Can clear=Yes
[11979.084991]   Enable PML: Can set=No, Can clear=Yes
[11979.089988]   EPT-violation #VE: Can set=No, Can clear=Yes
[11979.095590]   Conceal VMX from PT: Can set=No, Can clear=Yes
[11979.101379]   Enable XSAVES/XRSTORS: Can set=No, Can clear=Yes
[11979.107358]   Mode-based Execute Control for EPT: Can set=No, Can clear=Yes
[11979.114437]   Sub-page Write Permissions for EPT: Can set=No, Can clear=Yes
[11979.121509]   Intel PT Uses Guest Physical Addresses: Can set=No, Can clear=Yes
[11979.128935]   Use TSC Scaling: Can set=No, Can clear=Yes
[11979.134381]   Enable User Wait and Pause: Can set=No, Can clear=Yes
[11979.140769]   Enable ENCLV Exiting: Can set=No, Can clear=Yes
 
 
 
IA32_VMX_EXIT_CTLS 0x483(output )

 [11979.175429] Exit Controls MSR: 0x3fefff00036dff
[11979.180162]   Save Debug Controls: Can set=Yes, Can clear=No
[11979.185941]   Host Address-Space Size: Can set=Yes, Can clear=Yes
[11979.192235]   Load IA32_PERF_GLOBAL_CTRL: Can set=No, Can clear=Yes
[11979.198623]   Acknowledge Interrupt On Exit: Can set=Yes, Can clear=Yes
[11979.205356]   Save IA32_PAT: Can set=Yes, Can clear=Yes
[11979.210778]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[11979.216265]   Save IA32_EFER: Can set=Yes, Can clear=Yes
[11979.221789]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[11979.227218]   Save VMXpreemption Timer Value: Can set=No, Can clear=Yes
[11979.233961]   Clear IA32_BNDCFGS: Can set=No, Can clear=Yes
[11979.239758]   Conceal VMX from PT: Can set=No, Can clear=Yes
[11979.245563]   Clear IA32_RTIT_CTL: Can set=No, Can clear=Yes
[11979.251342]   Clear IA32_LBR_CTL: Can set=No, Can clear=Yes
[11979.257042]   Load CET state: Can set=No, Can clear=Yes
[11979.262398]   Load PKRS: Can set=No, Can clear=Yes

IA32_VMX_ENTRY_CTLS 0x484(output )

[11979.267309] Entry Controls MSR: 0xd3ff000011ff
[11979.271895]   Load Debug Controls: Can set=Yes, Can clear=No
[11979.277767]   IA-32e Mode Guest: Can set=Yes, Can clear=Yes
[11979.283453]   Entry to SMM: Can set=No, Can clear=Yes
[11979.288634]   Deactivate Dual Monitor Treatment: Can set=No, Can clear=Yes
[11979.295828]   Load IA32_PERF_GLOBAL_CTRL: Can set=No, Can clear=Yes
[11979.302221]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[11979.307566]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[11979.313006]   Load IA32_BNDCFGS: Can set=No, Can clear=Yes
[11979.318609]   Conceal VMX from PT: Can set=No, Can clear=Yes
[11979.324507]   Load IA32_RTIT_CTL: Can set=No, Can clear=Yes
[11979.330291]   Load CET State: Can set=No, Can clear=Yes
[11979.335721]   Load Guest IA32_LBR_CTL: Can set=No, Can clear=Yes
[11979.341975]   Load PKRS: Can set=No, Can clear=Yes
 
IA32_VMX_PROCBASED_CTLS3 0X92(output )
** AS TERITIARY MSR WAS NOT ENABLED IN MY SYSTEM
 
[11979.146727] Processor based Tertiary Controls MSR: 0x0
[11979.151981]   LOADIWKEY Exiting: Can set=No, Can clear=Yes
[11979.157586]   Enable HLAT: Can set=No, Can clear=Yes
[11979.162668]   EPT Paging-write Control: Can set=No, Can clear=Yes
[11979.168961]   Guest-paging Verification: Can set=No, Can clear=Yes




Overall Output :-
 
 [11978.809189] CMPE 283 Assignment 1 Module Start
[11978.813834] Pinbased Controls MSR: 0x3f00000016
[11978.818486]   External Interrupt Exiting: Can set=Yes, Can clear=Yes
[11978.824957]   NMI Exiting: Can set=Yes, Can clear=Yes
[11978.830134]   Virtual NMIs: Can set=Yes, Can clear=Yes
[11978.835387]   Activate VMX Preemption Timer: Can set=No, Can clear=Yes
[11978.842067]   Process Posted Interrupts: Can set=No, Can clear=Yes
[11978.848391] Processor based Controls MSR: 0xf7b9fffe0401e172
[11978.854258]   Interrupt Window Exiting: Can set=Yes, Can clear=Yes
[11978.860559]   Use TSC Offsetting: Can set=Yes, Can clear=Yes
[11978.866338]   HLT Exiting: Can set=Yes, Can clear=Yes
[11978.871566]   INVLPG Exiting: Can set=Yes, Can clear=Yes
[11978.877186]   MWAIT Exiting: Can set=Yes, Can clear=Yes
[11978.882545]   RDPMC Exiting: Can set=Yes, Can clear=Yes
[11978.887889]   RDTSC Exiting: Can set=Yes, Can clear=Yes
[11978.893358]   CR3 Load Exiting: Can set=Yes, Can clear=No
[11978.899102]   CR3 Store Exiting: Can set=Yes, Can clear=No
[11978.904703]   Activate Tertiary Controls: Can set=No, Can clear=Yes
[11978.911094]   CR8 Load Exiting: Can set=Yes, Can clear=Yes
[11978.916693]   CR8 Store Exiting: Can set=Yes, Can clear=Yes
[11978.922378]   Use TPR Shadow: Can set=Yes, Can clear=Yes
[11978.927806]   NMI Window Exiting: Can set=No, Can clear=Yes
[11978.933490]   MOV-DR Exiting: Can set=Yes, Can clear=Yes
[11978.939012]   Unconditional I/O Exiting: Can set=Yes, Can clear=Yes
[11978.945432]   Use I/O Bitmaps: Can set=Yes, Can clear=Yes
[11978.951128]   Monitor Trap Flag: Can set=No, Can clear=Yes
[11978.956741]   Use MSR Bitmaps: Can set=Yes, Can clear=Yes
[11978.962424]   MONITOR Exiting: Can set=Yes, Can clear=Yes
[11978.968027]   PAUSE Exiting: Can set=Yes, Can clear=Yes
[11978.973478]   Activate Secondary Controls: Can set=Yes, Can clear=Yes
[11978.980273] Processor based Secondary Controls MSR: 0x51ff00000000
[11978.986583]   Virtualize APIC accesses: Can set=Yes, Can clear=Yes
[11978.993095]   Enable EPT: Can set=Yes, Can clear=Yes
[11978.998268]   Descriptor Table Exiting: Can set=Yes, Can clear=Yes
[11979.004562]   Enable RDTSCP: Can set=Yes, Can clear=Yes
[11979.009913]   Virtualize x2APIC Mode: Can set=Yes, Can clear=Yes
[11979.016032]   Enable VPID: Can set=Yes, Can clear=Yes
[11979.021215]   WBINVD Exiting: Can set=Yes, Can clear=Yes
[11979.026649]   Unrestricted Guest: Can set=Yes, Can clear=Yes
[11979.032510]   APIC-register Virtualization: Can set=Yes, Can clear=Yes
[11979.039150]   Virtual-interrupt Delivery: Can set=No, Can clear=Yes
[11979.045531]   PAUSE-loop Exiting: Can set=No, Can clear=Yes
[11979.051239]   RDRAND exiting: Can set=No, Can clear=Yes
[11979.056678]   Enable INVPCID: Can set=Yes, Can clear=Yes
[11979.062290]   Enable VM Functions: Can set=No, Can clear=Yes
[11979.068068]   VMCS Shadowing: Can set=Yes, Can clear=Yes
[11979.073496]   Enable ENCLS Exiting: Can set=No, Can clear=Yes
[11979.079356]   RDSEED Exiting: Can set=No, Can clear=Yes
[11979.084991]   Enable PML: Can set=No, Can clear=Yes
[11979.089988]   EPT-violation #VE: Can set=No, Can clear=Yes
[11979.095590]   Conceal VMX from PT: Can set=No, Can clear=Yes
[11979.101379]   Enable XSAVES/XRSTORS: Can set=No, Can clear=Yes
[11979.107358]   Mode-based Execute Control for EPT: Can set=No, Can clear=Yes
[11979.114437]   Sub-page Write Permissions for EPT: Can set=No, Can clear=Yes
[11979.121509]   Intel PT Uses Guest Physical Addresses: Can set=No, Can clear=Yes
[11979.128935]   Use TSC Scaling: Can set=No, Can clear=Yes
[11979.134381]   Enable User Wait and Pause: Can set=No, Can clear=Yes
[11979.140769]   Enable ENCLV Exiting: Can set=No, Can clear=Yes
[11979.146727] Processor based Tertiary Controls MSR: 0x0
[11979.151981]   LOADIWKEY Exiting: Can set=No, Can clear=Yes
[11979.157586]   Enable HLAT: Can set=No, Can clear=Yes
[11979.162668]   EPT Paging-write Control: Can set=No, Can clear=Yes
[11979.168961]   Guest-paging Verification: Can set=No, Can clear=Yes
[11979.175429] Exit Controls MSR: 0x3fefff00036dff
[11979.180162]   Save Debug Controls: Can set=Yes, Can clear=No
[11979.185941]   Host Address-Space Size: Can set=Yes, Can clear=Yes
[11979.192235]   Load IA32_PERF_GLOBAL_CTRL: Can set=No, Can clear=Yes
[11979.198623]   Acknowledge Interrupt On Exit: Can set=Yes, Can clear=Yes
[11979.205356]   Save IA32_PAT: Can set=Yes, Can clear=Yes
[11979.210778]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[11979.216265]   Save IA32_EFER: Can set=Yes, Can clear=Yes
[11979.221789]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[11979.227218]   Save VMXpreemption Timer Value: Can set=No, Can clear=Yes
[11979.233961]   Clear IA32_BNDCFGS: Can set=No, Can clear=Yes
[11979.239758]   Conceal VMX from PT: Can set=No, Can clear=Yes
[11979.245563]   Clear IA32_RTIT_CTL: Can set=No, Can clear=Yes
[11979.251342]   Clear IA32_LBR_CTL: Can set=No, Can clear=Yes
[11979.257042]   Load CET state: Can set=No, Can clear=Yes
[11979.262398]   Load PKRS: Can set=No, Can clear=Yes
[11979.267309] Entry Controls MSR: 0xd3ff000011ff
[11979.271895]   Load Debug Controls: Can set=Yes, Can clear=No
[11979.277767]   IA-32e Mode Guest: Can set=Yes, Can clear=Yes
[11979.283453]   Entry to SMM: Can set=No, Can clear=Yes
[11979.288634]   Deactivate Dual Monitor Treatment: Can set=No, Can clear=Yes
[11979.295828]   Load IA32_PERF_GLOBAL_CTRL: Can set=No, Can clear=Yes
[11979.302221]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[11979.307566]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[11979.313006]   Load IA32_BNDCFGS: Can set=No, Can clear=Yes
[11979.318609]   Conceal VMX from PT: Can set=No, Can clear=Yes
[11979.324507]   Load IA32_RTIT_CTL: Can set=No, Can clear=Yes
[11979.330291]   Load CET State: Can set=No, Can clear=Yes
[11979.335721]   Load Guest IA32_LBR_CTL: Can set=No, Can clear=Yes
[11979.341975]   Load PKRS: Can set=No, Can clear=Yes

 
 


