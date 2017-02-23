Using cURL
====
You can easily interact with the M2X API using cURL, a powerful command-line tool for making HTTP calls.

*Pre-requisites: Windows 7 or later, or Mac OS X 10.7 or later (for this guide)*
*cURL itself works with almost any OS. You can find a full list here: http://curl.haxx.se/docs/install.html*

### Downloading + installing cURL on Windows
*(cURL is already installed on computers running Mac OS X)*

Use the following steps to install curl:

1. Open [http://curl.haxx.se/dlwiz?type=bin](http://curl.haxx.se/dlwiz?type=bin) in a browser.
2. Select your operating system in the dropdown box: either Windows, /Win32 or Win 64. Click Select!
3. For Win 32, choose whether you will use cURL in a Windows Command Prompt (Generic) or in a Cygwin terminal (cygwin). For Win 64, choose whether you will use cURL in a Windows Command Prompt (Generic) or MinGW (MinGW64). Click Select!
4. If required, choose your Windows operating system. Finish.
5. Click Download for the version which has SSL enabled.
6. Choose a version with support for SSL.
7. Open the downloaded zip file. Extract the files to an easy-to-find place, such as C:\Program Files.

### Testing cURL on Windows
Open up the Windows Command Prompt terminal. (From the Start menu, click Run, then type cmd.)

Set the path to include the directory where you put curl.exe. For example, if you put it in C:\Program Files\curl, then you would type the following command:

``
set path=%path%;"c:\Program Files\curl"
``

Now, type ``curl``
 
You should see the following message:

``
curl: try 'curl –help' or 'curl –message' for more information
``

This means that curl is installed and the path is correct.
Type:

``
curl https://api-m2x.att.com/v1
``

You should see JSON returned:

``
{
"message":"You must provide a valid API key in the X-M2X-KEY header"
}
``

### Testing cURL on Mac OS X
cURL is installed by default in Mac OS X. To test cURL, open up a Terminal Window (Terminal can be launched from Spotlight, the Dock at the bottom of the screen or even the Applications folder).

Type ``curl``

You should see the following message:

``
curl: try 'curl –help' or 'curl –message' for more information
``

This means that curl is installed and the path is correct.

Now, type:

``
curl https://api-m2x.att.com/v1
``

You should see JSON returned:

``
{
"message":"You must provide a valid API key in the X-M2X-KEY header"
}
``

### Advanced instructions
You can learn more about how to use cURL by visiting the official tutorials: [curl.haxx.se/docs/httpscripting.html](http://curl.haxx.se/docs/httpscripting.html)

### Troubleshooting
#### SSL certification error
If you see an SSL certification error, add a -k flag into your curl command.

#### https not supported error 
If you get an error that says, “Protocol http not supported or disabled in libcurl” then you need a different version of cURL. Make sure you have downloaded one that says SSL enabled. If you have downloaded the Win64 version, try the Win32 version instead, even if you are on a 64 bit machine.
