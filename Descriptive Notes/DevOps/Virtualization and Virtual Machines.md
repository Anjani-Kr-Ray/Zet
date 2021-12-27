# Virtualization and Virtual Machines
Imagine we have a computer with Windows installed on it. But we also need Linux OS for our work. Generally, we have to use another computer i.e., a seperate hardware will be required with Linux installed on it. But with `virtualization` no seperate hardware is required. We can install Linux on top of Windows and vice versa and this is possible only with Hypervisor.

Hypervisor is a technology that allows hosting many virtual OS on a physical host OS. One of the famous hypervisor is `VirtualBox` by `Oracle`. VirtualBox is Open-source application and works on all OS.

But it is important to know that: 
1. VirtualBox takes hardware resources from Host OS i.e., hardware resources are shared.
2. creates virtual CPU, virtual RAM, virtual storage for each virtual machine
3. We can only give resources we actually have

Virtual Machines are completed isolated from each other i.e., if something breaks inside VM, it **doesn't affect the host machine**

### Benefits of  a Virtual Machine
1. __Learn and Experiment__
	* You don't need to buy a new Computer for that
	* You don't need to endanger your main OS

2. __Test your app on different OS__

### Type 1 vs Type 2 Hypervisor
![](C:\Users\Anjani\Pictures\diff_hypervisor.jpeg "Type 1 vs Type 2 Hypervisor")

A __Type 1 hypervisor__ runs directly on the host machine's physical hardware, and it's referred to as a bare-metal hypervisor. The Type 1 hypervisor doesn't have to load an underlying OS. With direct access to the underlying hardware and no other software -- such as OSes and device drivers -- to contend with for virtualization, Type 1 hypervisors are regarded as the most efficient and best-performing hypervisors available for enterprise computing.

__Benefits:__

1. Efficient usage of resources:
	* use all the resources of a performant big server
	* users can choose any resource combinations

2. Hypervisors that run directly on physical hardware are also highly secure. Virtualization mitigates the risk of attacks that target security flaws and vulnerabilities in OSes because each guest has its own OS. This ensures an attack on a guest VM is logically isolated to that VM and can't spread to others running on the same hardware.

__Examples:__ `vmware ESXi`, `Microsoft Hyper-v`, any virtual machines created on cloud platform like `AWS`, `Digital Ocean` etc are of Type 1.

A __Type 2 hypervisor__ is typically installed on top of an existing OS. It is sometimes called a hosted hypervisor because it relies on the host machine's preexisting OS to manage calls to CPU, memory, storage and network resources.

__Benefits:__ 
* Good for personal use

__Examples:__ `VirtualBox`, `Parallels Desktops`, `QEMU` etc

### Why are companies adopting Virtualization?
**Abstraction of the Operating System from the Hardware**
 1. Without Virtualization
	* company managed their own servers themselves
	* used to install OS on the server and then install application and set the required configuration files on their own
	* OS is tightly coupled to the hardware here i.e., if for any reason hardware fails and we're unable to fix it then every thing will be lost. This caused one point failure
2. With Virtualization
	* We have OS as a portable files and these files are nothing but `Virtual Machine Images`. This VM image includes OS and all applications installed on it with all the configuration files, documents etc.
	* As it is a file we can make backup of our entire OS and these backups are nothing but snapshots. So if any thing happen to VM image, we can take these snapshots and run it on hypervisor and we will get back our OS.
	* This helps us make OS portable as well as more secure. 