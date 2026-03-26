# Setting up a Local new site on your Laragon Server
I found out that laragon can serve a web sites on your PC from any folder on any drive
on your pc and you can name it with any name and any TLD you want. 
All you need to do is this:
1. Create a file name
<you-domain>.<your-TLD>.conf in the C:\laragon\etc\apache2\sites-enabled folder
At the top of the conf file edit these lines:
```
define ROOT "<Path with forwaed slashes>" 
define SITE "<your-domain>.<your-TLD>".
```
Note: Don't put and ending slash (/) in either path. 
For example, let set a site named mike.smith in `F:\Docs\M-Smith`
```
define ROOT "F:/Docs/M-Smith"
define SITE "mike.smith"
```
Leave the rest of the file alone. the lines created an http://  and https://
site for you with SSL enabled.
2. The last step needed is to have the domain listed in Windows hosts file.
C:\Windows\System32\drivers\etc\hosts file with the line:
```
127.0.0.1 <your-domain>.<your-TLD>  # Your comments here with path to your site
```
- That's it. You'r all set. Restart your Laragon Server.
The site should be up and running.
