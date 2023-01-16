# IBM Aspera Products Lab

## About this Lab

In this lab, you will learn:  
-	To install and configure HSTS.  
-	To install and configure Console.  
-	To install and configure Shares.  
-	To install and configure Faspex5.   
-	To integrate HSTS to Console, Shares and Faspex5     
-	To create users and authorize users in Shares.  
-	To create users and authorize users in Faspex5.  
-	To use different clients to transfer files.    
-	Basic Functionalities of Console.  

### References

HSTS: [https://www.ibm.com/docs/en/ahts/4.4](https://www.ibm.com/docs/en/ahts/4.4).  
Console: [https://www.ibm.com/docs/en/aspera-console/3.4](https://www.ibm.com/docs/en/aspera-console/3.4).  
Shares: [https://www.ibm.com/docs/en/aspera-shares/1.10](https://www.ibm.com/docs/en/aspera-shares/1.10).  
Faspex5: [https://www.ibm.com/docs/en/aspera-faspex/5.0](https://www.ibm.com/docs/en/aspera-faspex/5.0).  


### Software Download

All needed software can be downloaded from:   
[https://www.ibm.com/products/aspera/downloads](https://www.ibm.com/products/aspera/downloads).  
From this page, you can pick the needed software. Make sure to download linux version of the software.

### Licenses

Evaluation Licenses can be obtained from: [https://ibm.box.com/s/3e35cd8m3eaqpndeuc9e51igqtxl2u4l](https://ibm.box.com/s/3e35cd8m3eaqpndeuc9e51igqtxl2u4l).  
Evaluation licenses are normally valid till end of the month. 

### Learning Paths
There are 2 paths for learning the Aspera products here. Suggestion will be to start with Path 1 and then move on to Path 2. 

Path 1 – HSTS, Console and Shares (Estimated time: 2 hours).  
![](images/image01.jpg)    

Path 2 – HSTS and Faspex5 (Estimated time: 1 hour).  
![](images/image02.jpg)   

## Lab Prerequisites

1.	Three servers (physical or VM) with at least 2 cores, 8GB RAM and 10GB storage. CentOS 7.x or RHEL 8.x operating system. [ This hardware spec and co-hosting of components is for lab purposes only. NOT suitable for customer environment] 
2. In this lab document, we will refer to the systems by 3 names, HSTS, Console, and Faspex.   
3.	Login to your servers using Mac terminal or Putty (Windows users). If you do not have root access, you will have to use sudo to run the commands. 
4.	The following installation software should be downloaded and made available in a local folder (e.g. /opt/software). 

System1 (HSTS):
>    
ibm-aspera-hsts-\<version>-linux-64-release.rpm.   
ibm-aspera-hsts-\<version>-linux64-public-key.pgp.zip.   
Inside /opt/software/shares:    
ibm-aspera-shares-\<version>.x86_64.rpm.   
There will also be PDF documentation files in these directories.     


System 2 (Console):   
>    
ibm-aspera-common-\<version>.x86\_64.rpm.  
ibm-aspera-console-\<version>.x86\_64.rpm.  
IBM\_Aspera\_Console\_\<version>\_Linux\_Windows\_Patch\_Level\_\<version>.zip.  
There could be multiple patch files. Download all the patches.   
There will also be PDF documentation files in these directories.  

System 3 (Faspex):
>    
ibm-aspera-faspex-\<version>.x86\_64.rpm.  
There will also be PDF documentation files in these directories.  

5.	Licenses shoudl also be downloaded to a local foler (e.g. /opt/software).   

> shares-license-<date>.txt in System 1.  
console-license-<date>.txt in System 2.    
hsts-license-<date>.txt in System 1.    

6. Stop and Disable Firewalld (note this is only for lab purposes – for a real install on a publicly available system, we would properly configure the firewall).  

> Check: systemctl status firewalld  
Disable: systemctl disable firewalld  
Stop: systemctl stop firewalld  


7. Set selinux to permissive.    
Edit /etc/selinux/config. Change the line that starts with “SELINUX” to the following, if not already set this way.   

	`SELINUX=permissive`.  

	If a change was made, Save the file and Reboot the machine.  
	
8.	Access to a SMTP server (Mandatory for Faspex5. Optional for Console and Shares). 
For this lab, we will use the following SMTP relay for email notifications.  This relay is not guaranteed to be around for very long after this training session, so you may have to use the GMAIL configuration as described at the end of this document.

> Server: smtp.sendgrid.net.  
Port: 587.  
Username: apikey  
Password: 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  
   


## Install Transfer Server on HSTS system

