# H3

## Article Summaries

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

Next, I made sure my Linux was updated. Initially I tried inputting the update commands into the same command line window that I used to start up WebGoat, and unfortunately it did not work. I initially thought I was inputting the commands wrong, and tried different ways to write them as you can see in this screenshot.

![Error when updating]()

I then got it to work by inputting the commands into a fresh command window.

![Updating success]()



## SQLZoo

## Portswigger Labs

This was relatively easy to solve with the provided information from the Portswigger website however, understanding *why* this was the solution took quite a bit longer.

![SQL Injection](https://github.com/chelsea-12/chelseaexamples/blob/main/Screenshot%202024-01-31%20092041.png)


