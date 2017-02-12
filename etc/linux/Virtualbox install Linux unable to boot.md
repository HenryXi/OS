# Virtualbox install Linux unable to boot
After creating virtual machine I want to install CentOS6 (32bit). I got the error message like following. 
```
This kernel requires the following features not present on the CPU:
pae
Unable to boot - please use a kernel appropriate for your CPU.
```
This message means you CPU (virtual) does not support PAE. About PAE you can click [here](https://en.wikipedia.org/wiki/Physical_Address_Extension) 
for more detail. Put simply, 32 bit system can't use more than 4G of memory address space without PAE. 

**Solution**

Enable PAE: go "Settings" -> "System" -> "Processor" and enable "PAE/NX".