# SubrionCMS-4.2.1-File-upload-RCE-auth-
This is an edited version of the CVE-2018-19422 exploit to fix an small but annoying issue I had.

I had to use this exploit in a CTF but I could not get it to properly exploit, just kept failing to login. After an unholy amount of time I finally figured out why. It was an issue with the url argument. When I specified a url, the program automatically assumed that I would end it with a / which I didn’t do.
What I was doing:
http://example.com
What I was suppose to do:
http://example.com/

What annoyed me even further was that even in the help menu the example is:
http://target-url/panel
Doesn’t end in a backslash but the program won’t work if you specify the url like this.
So I made a quick edit that checks the last character of the url arg to make sure that it ends with a slash.
