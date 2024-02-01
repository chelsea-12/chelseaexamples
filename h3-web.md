# H3

## Article Summaries from OWASP 10 2021

### [Security Misconfiguration](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)

- a shift into more highly configurable software has seen more incidences of some form of misconfiguration
- a few examples of when applications could be vulnerable: unnecessary features are enabled or installed, default accounts are still enabled and passwords unchanged, the software is out of date or vulnerable.


### [Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)


### [Injection](https://owasp.org/Top10/A03_2021-Injection/)

## WebGoat 2023.4

I managed to install WebGoat during class time and everything went well, apart from needing to take one additional step during the process. Before downloading the WebGoat JAR using the wget command, I needed to first install wget. This was done through this simple command: 
> $ sudo apt-get install wget

I also solved the Developer Tools during class time. This actually took more time than it should have due to my Linux screen being impossibly small. This was solved by installing guest additions to VirtualBox; a classmate helped me to do this (thanks, Pan!) but if you run into this issue, hopefully [this](https://terokarvinen.com/2021/install-debian-on-virtualbox/) helps (scroll down to find the relevant section).

Once this small, but very large, issue was solved I was able to move on.

I started up WebGoat by inputting this into the Command Line on Linux.

![WebGoat](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-01%20100807.png)

The first task in the Developer Tools section was straightforward and involved inputting a command into the console window and getting a return value.

![First Task](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-01%20101131.png)

The second task stumped me for a little longer. We needed to enter the Network tab, generate an HTTP request on the website and find the Network Number. When generating an HTTP request, the Network tab shows a large number of GET responses, whereas we are looking for the POST response. If you are not fast enough with locating this, it can get lost in the list. Once you click on the POST response, I then needed to navigate to the request tab to find the required number. It took a bit of clicking around on the different tabs to figure this out.

![Second Task](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-01%20101200.png)

Next, I made sure my Linux was updated. Initially I tried inputting the update commands into the same command line window that I used to start up WebGoat, and unfortunately it did not work. I initially thought I was inputting the commands wrong, and tried different ways to write them as you can see in the bottom of this screenshot.

![Error when updating](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-01%20101706.png)

I then got it to work by inputting the commands into a fresh command window.

![Updating success](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-01%20101727.png)


## Portswigger Labs

This was relatively easy to solve with the provided information from the Portswigger website however, understanding *why* this was the solution took quite a bit longer.

![SQL Injection](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-01-31%20092041.png)

My understanding is that SQL injection is when someone tries to extract information from your web server by inserting malicious SQL (SQL being the programming language for databases) code. In this instance, the malicious code is inserted via the website's URL. We are attempting to see items that are not otherwise possible to view. By navigating to the website and clicking on 'Gifts', we are sending an SQL query to retrieve the requested items from the database and display them. This is what the SQL query is asking: FROM products WHERE category = 'Gifts' AND released = 1.

The most crucial part here is the = 1. This is a restriction that ensures only released products are shown. 

If we add the following onto the end of the URL, it manipulates the system into showing the unreleased products

> '+OR+1=1--

As 1=1 is always a true return (Boolean condition), this returns all items. The ' at the start is crucial, as this checks for anomalies. Likewise the -- is also crucial as it is a comment indicator, meaning anything after that is treated as a comment and ignored. In this case, it is ignoring the 'AND released = 1' which would show us only the released items.


## SQLZoo


SQLZoo helped me to understand the Portswigger Lab better, as it went to a more basic level about SQL commands and queries. This was extremely helpful to broaden my understanding! Part 0 invovled modifying the SQL commands to yeild different results.

![Basics SQLZoo](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-01%20112909.png)

The second part ot this exercise delved into this in more detail and at times I needed to call on some of my programming knowledge from my previous 'Introduction to Software Development' course. Such as with this example where I needed to show countries with a population equal to or greater than 200 million.

![SQLZoo Part 2](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-01%20113317.png)

These exercises got increasingly more complicated as I went on, and I found the helpful hints and the previous 'BASIC' page key to solving the issues. It was a very good exercise to not only see what SQL commands can be used, but to actually write and input them myself which I find helps with memory retention.

I also found [this](https://thedatasleuth.github.io/2018/08/11/SELECT-Basics.html) website helpful if I got really stuck with any exercise, such as with this one. I wasn't sure what the syntax was for searching for a name that inludes something. In this case 'United' (although if I had completed Exercise 1 from SQLZoo, this would have helped also!).

![Percentage syntax](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-01%20115230.png)

The final exercise took a bit of time to solve as I did not initally think I needed to include a new 'AND' in between all of the conditions.

![Final exercise](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-02-01%20120920.png)


The IN, LIKE, NOT LIKE, XOR, ROUND, LEFT and LENGTH function are new to me as I have only learnt Javascript so far. Likewise expressing 'not equal to' as '<>' is new for me. It's interesting to learn the different ways to express these in new languages. 

**Overall, I really enjoyed this introduction to hacking and it's extremely interesting learning about the potential flaws in systems that can be taken advantage of. I look forward to learning about this in more detail on this course.**
