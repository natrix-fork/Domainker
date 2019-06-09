# Domainker
![](https://raw.githubusercontent.com/BitTheByte/Domainker/master/lib/banner.png "Logo Title Text 1")
# Setup
Python pypi package got removed. if you want to use this tool follow the steps below
- Manual setup 
```
git clone https://github.com/BitTheByte/Domainker
cd Domainker
python domainker.py
```
 
 
# How to use
I developed this tool to be easily managed and upgraded so i created it as small plugin systems connected together

## Plugins and usage
```
lib\plugins\experimental\cache_poisoning.py : [--cache-poisoning] Check if the host is vulnerable to cache poisoning
lib\plugins\crlf.py   : [--crlf] Check if Host is Vulnerable To CRLF
lib\plugins\aws.py    : [--aws] Check if The Target is found on Amazon + Automatic uploading
lib\plugins\cname.py  : [--dns] Return Target cname
lib\plugins\url.py    : [--url] Return Target Response Code [See the options for more details]
lib\plugins\struts.py : [--struts] Attack Struts [CVE-2018-11776]
lib\plugins\put.py    : [--put] Check if [PUT] Method is Enabled
lib\plugins\spf.py    : [--spf] Check For SPF Record
```

## Basic usage
 ```
 $ domainker -i google.com [.. Plugins]
 $ domainker -d mydomains_list.txt [.. Plugins]
 $ domainker -d mydomains_list.txt --url
 $ domainker -d mydomains_list.txt --dns
 ```
You could also use multiple plugins at the same time
```
$ domainker -d mydomains_list.txt --url --dns --aws ...
$ domainker -i google.com --url --dns --aws ...
```
## Options
```
$ domainker --help
```
- Create output file [--output/-o file_name]
- Threads count [--threads/-t number]
- Interesting files search [--interesting-files/-F] [--url / --all required]
- Thread timeout [--thread-timeout/-T seconds]
- Request timeout [--request-timeout/-rt seconds]


# Format 
I want to add different formats at the future but currently this tool only supports this formats for the input file
```
https://sub.domain.com  
http://sub.domain.com  
sub.domain.com  
.sub.domain.com
```
Which generated by:
- amass  
- aquatone (hosts.txt)  
- subfinder  
- sublist3r  
... and many other subdomain finders  

# Contributors
- [k3r1it0](https://github.com/k3r1it0)
- [NeuroWinter](https://github.com/NeuroWinter)
- [GeneralEG](https://github.com/GeneralEG)

# FAQ
[Q] Why it's called Domainker?  
[A] Originally this was a just checker script for domain availability so the name was originated from [Domain-Checker]
  
[Q] What is the tool for?  
[A] This tool for bugbounty hunters to help them automate the boring tasks and find some low hanging bugs  
  
[Q] Which Python version should i use?   
[A] Python 2.7.15 or later  
  
[Q] Does this tool support Python3?   
[A] Python3 support hasn't been tested at the current time but i'm planning to make it available soon  

[Q] I have an idea for you, what should i do?  
[A] If you have already implemented your idea please make a pull request if not or don't know how to do it please open a new [issue](https://github.com/BitTheByte/Domainker/issues) describing your idea in it
