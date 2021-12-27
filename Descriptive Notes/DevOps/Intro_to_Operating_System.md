# Intro To Operating System

### What is an Operating System?
Every computer is made up off some hardware like `CPU`, `Memory`, `Storage`, `IO Devices`(such as Screen, Mouse, Keyboard) and as an `User` we need to interact with these hardware. So, how can we do that? Well! Well! First let's take an example of an software application, say `Google Chrome`. It needs to access `CPU` and `Memory` to **process data** and `Keyboard and Mouse` to take input from the user and screen to display result. But does software application, here Google Chrome, know how to take input from keyboard and mouse and display the result or allocate memory and CPU to do its job. **Well, it doesn't**. Software application can't be installed directly on the hardware because if it did then every application must have the code to talk to hardware components of computer.  

So, it was very important to have an intermediary application which could help software application communicate with hardware. The answer was Operating System. **An `Operating System` is a program that controls the execution of application programs and acts as an interface between the user of a computer and the computer hardware. It also `manages resources among applications` and also `isolates content of applications` so that they don't intefere with each others resources.**

### What are the OS tasks?
##### 1.  Resource Allocation and Management
Operating System is reponsible for allocating and managing hardware resources like CPU, Memory, Storage and IO Devices.

1. Process Management
	* managing CPU Resources
	* If you open Activity Monitor(on MacOs) or Task Manager(on Windows) you will find multiple process running in the background and each process will have some share of CPU allocated to it. But, what is a `process`?
	* Process is a small unit that executes on computer. Each process has own isolated space so that there is no interference between different processes.

	> Note: If a computer has 1 CPU then it can process 1 task at a time. So if you're thinking how we can listen to music while surfing on browser or while writing some documents etc., then it happens because CPU switches between the tasks so fast that we don't notice it and have illusion of parallel processing or multitasking.

2.  Memory Management
	* allocates working memory(RAM) to the process 
	* every application needs some data to work
	* But RAM is limited on the computer. If many processes are running then we might run out off memory. This is the case where `Memory Swapping` takes place
	* OS makes a process inactive or swaps-out a process by clearing its resources from RAM and stores it on storage devices. Now some part of RAM is available for use so OS swaps-in another process to RAM. This whole process is called `Memory Swapping` and it generally slows down our computer because loading and unloading of data takes time.

3. Storage Management
	* also called `Secondary Memory`
	* persisting data long-term
	* The data of an application is loaded into RAM while we are working on it. But after our work we want to save data permanently on our computer so that it is available whenever we open the application again.
	* OS stores these permanent files in a structured way. In UNIX systems the file structure is in tree form whereas Windows has multiple root folders but in hierarchical manner

4. Management of I/O Devices 
	* OS knows how to handle and translate interactions between apps and devices.

5. Other Services
	* Security
		* managing users and permissions
		* each user has its own pace
		* each user has permissions
	* Networking
		* ports and IP address

### Operating System Components
1. Kernel
	* Heart of the OS. It is a program which consists of device drivers, dispatcher, scheduler, file system etc.
	*  loads first
	* It resposible for managing hardware components
	* It also handles various I/O devices using `Device Drivers`. Device drivers are programs which helps various external devices to interact with computer.
	* It is the layer which helps applications interact with hardware.
	* kernel starts the process and allocate memory for application and also cleans up the resources when application shuts down.
2. Application Layer
	* Different linux distribution have different application layers, but based on same Linux Kernel
	* They have different icons, color themes, GUI looks different and also have different application installed in the package

	> __Points to remember:__
	> 
	> Operating Systems for Servers:
	> * mostly based on linux
	> * more __light-weight__ and performant
	> * No __GUI__ or other user applications
	> * Half of server world wide use Linux OS tough there are windows servers
	
	 > __Question:__
	 > How to interact with kernel?
		 >* using `GUI` or `CLI`
	



