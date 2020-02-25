#### XenServer - Enable Container Management
supporting Container (like Docker) nativly on XenServer

1. Login to your XenServer via ssh

2. Download the container supplemental-pack  from <i>package</i> folder above

3. Install the XenServer xscontainer.iso plugin to enable Container management
<pre>
xe-install-supplemental-pack  XenServer-<VERSION>-xscontainer.iso
</pre>

##### Final Step
Create new VM typically on Xen and select CoreOS as template 
Give your credentials and other settings in CloudInit script
(e.g. your ssh public key).

The CloudInit settings are default configs for your new container(s) on coreOS


ScreenCasts

Containers on Xen GUI
![xen-container-mananagent](https://aysadcloudns.cc)

Benchmark container
![xen-container-benchmark](https://aysadcloudns.cc)

#### some words

In general, virtualization is nothing more than using the software of the original operating system, e.g. Linux in let's say an 8-core intel processor, and virtualize a machine with a 2-core machine with code for ARM that runs on an x86 machine. This process of generating a virtual machine that runs on top of other machine is called virtualization. I think we became familiar with qemu and other projects like that to emulate mobile devices and other processors, back then they were called "Emulators". 

However, virtualization is nothing different in terms of the same effect, it might differ in terms of kernel and driver usage, which is called in general as a HyperVisor. 

In simple words, a HyperVisor is nothing more than an Operating System designed to run virtual machines in an efficient manner. As such we have XenServer, KVM, VMWare, hyper-V or even VirtualBox
