##PyFTP

PyFTP is a better FTP module for Python that builds on top of the default ftplib module. It aims to provide better access to the methods given in ftplib and reduce code repetitiveness.

This module is under development.

###Why build it?

Python's default `ftplib` module, altough fairly powerful, isn't intuitive and simple to use at all. Most of the default methods require using FTP commands as parameters and a lot more.

For Example, to upload a file in ftplib, you need to use the following code:

```
from ftplib import FTP

ftp = FTP(host='127.0.0.1')
ftp.login()
ftp.storbinary("STOR newname.jpg" , open('img.jpg','rb'))
```

Wait, what is STOR above? Can't Python write that out itself. There is a reason behind that, that is that We can supply another command in place of STOR above. Nice, but most of the time we will be using STOR itself. So there is no need for different commands. In the end, whenever we want to upload files, we will have to write more code.

That is where PyFTP fits in. The repetitiveness is handled by the module itself and you have simpler methods to work with.

In PyFTP, the above code becomes:

```
from ftp import ftp 

con = ftp(host='127.0.0.1') #You are automatically logged in
con.writefile('img.jpg', newname='newname.jpg')
```

See, the entire usage pattern becomes much simpler. Similarly, PyFTP provides different and easier methods for working with ftplib.

Infact, my vision for PyFTP is somewhat like what requests is to urllib. requests is far more easier and better for accessing HTTP resources thatn urllib and PyFTP should become something like that too.

###Inheriting from FTP

In case, any API is not available in PyFTP, you can use the good old ftplib commands with PyFTP too. Because, the `ftp` class of PyFTP inherits from the `FTP` class of ftplib.

###About

PyFTP is under development. PyFTP will be extensively used in my upcoming program, Zoe which provides FTP access to git. 

Created By Pradipta. Copyright 2015. MIT Licensed.

