**Importing data through FTP for data above 10GB**
==================================================

* For data above 10GB, uploading directly through the server could slow down or halt the server itself

* Hence, use the FTP as default whenever possible. For carrying out the FTP transfer, download `FileZilla <https://filezilla-project.org/>`_. It is a free software and easy to use

* Once downloaded and installed, you are ready to start your FTP transfer. On the upper left-hand side, there is a symbol (Hovering above it should show up as "Open the site manager. Right-click for a list of sites")

* Click on this symbol, and a textbox should show up. Enter Protocol as "FTP - File Transfer Protocol", Host as "esplgalaxy01.csmc.edu", Encryption as "Only use plain FTP", Logon type as "Normal", User as your username (without csmc.edu) and Password as your password that you used for Galaxy. Click "Connect"

* This should connect to the Galaxy server. On the left-hand side is the files in your computer and on the right-hand side is the server. Double-click on the file that you want to transfer to the server. It shouldn't take too long for the transfer. Do this for all the files that you want to transfer

* Now, go back to the Galaxy web server and click on upload data. In the textbox that appears, click on "Choose FTP files", all the files that you transferred to the server through FileZilla should show up. Click on the box next to the files that you would like in your current history and click "Start"

* This should bring the files that you transferred to your current history in Galaxy
