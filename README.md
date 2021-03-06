# limitedinternet

Currently only works with **systemd**.

**WARNING: THERE IS A BUG**
To make the script work, after the first time you run it, manually edit the file /etc/.nsswitch.conf.limited.internet.on
and from the line  that starts with **hosts**, delete the word **dns** (if it's there).
This will be fixed.

## How to use
**limitedinternet on**: enable limited mode (access to certain websites only)  
**limitedinternet off**: disable limited mode (access to all websites)

* In the directory you downloaded the script, create a file called **websites.txt**.
* This files should contain all the websites you want to have access to, when on limited mode.
* Write a website per line.

Example websites.txt file:

```
www.facebook.com
youtube.com  
reddit.com
```
(Don't write https:// or http//)  
(You may need to restart your browser after turning limitedinternet on.)

That's it!

### If you use `/etc/hosts` for other purposes read on

In case, you want to add additional entries to your `/etc/hosts` either when limitedinternet is on or off,
create 2 files on the directory the script was downloaded:

* `other_on.txt`  
additional entries for when limitedinternet is on
* `other_off.txt`  
additional entries for when limitedinternet is off

Those files are appended to `/etc/hosts` as is. So, they must be (ip address, domain name) pairs separated by whitespace.

Example `other_off.txt` file:
```
1.2.3.4     my.name
1.1.1.1     wo.w
```
