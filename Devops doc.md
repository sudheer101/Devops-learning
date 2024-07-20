
# Devops Documentation
# Author: Sudheer kuna

## Topics

- [About Devops](#AboutDevops)
- [Linux commands](#Linuxcommands)
- [Git and GitHub](#GitGitHub)
- [Cloud (Azure/AWS)](#Cloud (Azure/AWS))
- [Terraform](#Terraform)
- [Kubernetes](#kubernetes)
- [Ci/cd Deployment](#Ci/cdDeployment)
- [PowerShell](#PowerShell)
- [Shell scripting](#Shellscripting)
- [ARM templets](#ARMtemplets)
- [Yaml](#Yaml)

##  About Devops


### Devops:
 Development and operation from managing the source code to deploying the end product.

It’s a culture that imposes an organisation to deliver the application.

Main uses of devops
-	Improving Delivery
- Automation
-	Quality
-	Monitoring
-	Testing

Devops is a process of improving the application delivery by ensuring proper automation, quality, monitoring/observability, testing.
End goal is to avoid the manual errors/work.

### Why devops
Before devops in order to deliver a product to end user/clint there were lot of manual work used to be performed (testing, build manager, system adimin) now using devops we have automated few stages with certain tools.

 ### Software Development life cycle
**SDLC** : it is process that is followed by the organisation to Design Develop & test in order to maintain the high quality service.

**Stages**:
- Planning: Gather required information related to product. 
-	Defining: Documentation, software requirement
-	Designing: High level design (HLD), Low level design (LLD)
-	Building: Develop writing code and other tools that required.
-	Testing: Will test does all the features or software is working as expected
-	Deploy: Deliver the product that we have produced.

Devops eng will fasten the process of build, test, deploy. ensures the high quality of the application. 


---



# Linux OS & basic shell scripting

**O.S**: Operating system is used to run software on the hardware, it act as a bridge between hardware and software.

 ![linuxos](<linux os.png>)                                         

**Linux** : It is a open source operating system which is most popularly used in the software community is also more secure.
Secure: no need to install the antivirus
Distributions: cent o.s, ubuntu, Debin
Common Features
1.	Multi-user Capability: Multiple users can use the system simultaneously without interfering with each other.
2.	Multitasking: Linux can run multiple processes at the same time.
3.	Portability: Linux runs on a wide variety of hardware platforms.
4.	Security: Linux has robust security features, including user permissions and SELinux (Security-Enhanced Linux).
5.	Open Source: Linux is released under the GNU General Public License (GPL), allowing anyone to use, modify, and distribute the software.
6.	Fast: o.s is very fast to take the request and response


### Architecture 

            
Kernel: The core part of the operating system that manages hardware resources and provides essential services to the system's software.
•	Device management
•	Memory management
•	Process management
•	Hardware system related calls


# Shell Scripting

**shell** : It is use to talk to o.s using command’s we will call them as shell commands.

On servers mostly we won’t use GUI as it is more viable to carry it on the server. So we use the shell commands to interact.

Commands: 
Here are some essential Linux commands to get you started:
- ls: Lists files and directories in the current directory.
-	cd: Changes the current directory.
-	pwd: Prints the current working directory.
-	cp: Copies files or directories.
-	mv: Moves or renames files or directories.
-	rm: Removes files or directories.
-	mkdir: Creates a new directory.
-	rmdir: Removes an empty directory.
-	chmod: Changes file permissions.
-	chown: Changes file ownership.
-	ps: Displays information about running processes.
-	top: Shows real-time system resource usage.
-	grep: Searches for patterns in files.
-	find: Searches for files and directories.
-	tar: Archives files.
-	curl: Transfers data from or to a server.
-	ssh: Connects to a remote machine via Secure Shell
-	cd .. :go back to one directory
-	cd../.. :two directories back.
-	Ls-ltr: it provides all the directory, files, owners ,sizes & time stamp
-	touch: to create file
-	free -g: what is memory of the server
-	nproc: cpu usage
-	df -h : disk size
-	top : complete info
-	vi: create and write into the file.
### Vi editor
~~~
>v
i –(insert)
<script/data that user defined values>
:wq! (to exit from the files by saving all the data)
:q!(without saving the data).

~~~~


**How to write shell scripting** 

~~~
>touch <filename.sh> --> creates a file
>pwd/ls
>ls -ltr
>vi <filename.sh>
script
:wq!
~~~

touch and vi is similar but touch will help to open the multipule file.

#!/ --> shebang
#!/bin/bash 