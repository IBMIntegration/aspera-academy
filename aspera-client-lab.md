# Test Aspera Clients

The objective of this lab is try the Aspera based transfers and compare the speed of Aspera Transfers against SCP transfers (e.g. using FileZilla).   
You will also test the latest web application (Faspex 5). 

## Compare Speed

You will test transferring a file (around 100MB) using SCP [e.g. Filezilla] and also Aspera Desktop Client. 

1. First test transfer using Filezilla (or any other file transfer client).  
2. Download Install FileZilla from [here](https://filezilla-project.org/download.php?type=client).   
3. Open FileZilla and establish a connection to the Aspera Server.  Connection Details:   
	
		Protocol: SFTP
		Host: <HSTS-HOSTNMAE>
		Port: 33001
		Login Type: Normal
		User: Use your Login ID (e.g. user15)
		Password: Use your password. 
		
	
	![](images/image62.jpg)
	
4. Click on Connect and initiate a transfer. Take note of how long it takes to transfer.   

	![](images/image63.jpg)



1. Next, do a similar test with. Aspera Desktop Client.   
2. Download and Install Aspera Desktop Client from [here](https://www.ibm.com/products/aspera/downloads).  
3. Open Desktop Client and establish a connection to the Aspera Shares Server.  Connection details:

	Click on Connection and then the "+" sign.   
	
		Host: https://<SHARES-URL>
		User: Use your Login ID (e.g. rajan@my.ibm.com)
		Authentication: Choose Password
		Password: Use your password. 
		
	![](images/image64.jpg)
	
1. Click on OK. Then, double-click on the connection to establish connection and initiate a transfer. Click on the Details tab to check how long it took to transfer the file.   

	![](images/image65.jpg)
	
2. Larger files will show more improvement.   


## Take a preview of Faspex 5 

1. Open [this URL](https://aspera-techjam.asperademo.com/aspera/faspex/) and create an account.  
2. Enter the details and click on create.   
3. Account approval has been turned off - so, you can start logging in and test the features immediately.   
4. Discover features like sending files, sending invitation links, installing the connect plugin and extension.   

## Try yourself.

1. It is possible to setup Aspera Connect to be able to automatically download packages received and send packages from Windows Explorer. Explore these features. 

[Windows User guide](https://www.ibm.com/docs/en/aspera-connect/4.2?topic=windows-working-aspera-faspex).  
[MAC user guide](https://www.ibm.com/docs/en/aspera-connect/4.2?topic=macos-working-aspera-faspex).  



