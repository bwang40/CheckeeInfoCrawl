
********************************************************
CheckeeInfo data Crawl and Analysis with Python 3
********************************************************

.. contents:: Table of Contents
   :depth: 2
   
Introduction 
=======================
On the 93rd day after my F1 VISA renewal application is under administrative processing. I decided to create this project to crawl the data on the checkee.info website. I am waiting for my VISA to get processed for over three months. Life is so miserable while waiting. Hopefully this situation is going to get better in the future.

In the beginning, I decided to use python class to define each application. However I end up use list of list to contain all the data. This is simply because I think it is more efficient for simple application like this. I can operate the list freely without concerning too much about memory issue.

The code is written in python 3 using the Jupyter of ANACONDA. (Easy to setup, all the libraries are loaded with the original ANACONDA)

Simply open the file  `CheckeeCrawl.ipynb <https://github.com/bwang40/CheckeeInfoCrawl/blob/master/CheckeeCrawl.ipynb>`_ with jupyter 

update on July 2019:
-------------------------
Driven by curiosity, I run the program again to view the status of the checked cases for visa. I found that we are not experiencing the worst case scenario. Indeed that the checked cases and long check cases are increased over 201912-201902. However compare to some other times, it is still a very small peak on the graph. 

update on March 2020:
-------------------------
The data shows that the checking cases has increased over the previous year.

The checkee.info_ website is organized by month, each independent month has its page with all cases been checked in that month. The code starts with creating a list of websites in the time range that I am interested in with the following code::
    
    #Function to create time list
    def ListofTime_generator(StartYear,StartMon,EndYear,EndMon):
        ListofTime = []
        while(StartYear!=EndYear or StartMon!=EndMon):
            ListofTime.append(str(StartYear) + "-" + str(StartMon).zfill(2))
            if StartMon == 12:
                StartYear += 1
                StartMon = 1
            else:
                StartMon += 1
        ListofTime.append(str(EndYear) + "-" + str(EndMon).zfill(2))
        return ListofTime
    StartYear,StartMon,EndYear,EndMon = 2008,12,2021,1
    ListofTime = ListofTime_generator(StartYear,StartMon,EndYear,EndMon)


Some Example Output
=======================

The monthly long check cases (above 60 days) is using the secondary axis on the chart, Blue stands for AVG checking time for long checks of that month, red represents for longest checking time for that month. Data shows that the long check cases has dramatically increased in 2019.

.. image:: https://github.com/bwang40/CheckeeInfoCrawl/blob/master/image/longcheck.PNG
   :scale: 25

The following chart is the monthly average waiting time over the past 11 years. Data shows that the waiting time over the past few years has remains the same, slightly increased in 2019.
   
.. image:: https://github.com/bwang40/CheckeeInfoCrawl/blob/master/image/checkAVGbymonth.PNG
   :scale: 25

These two pie charts shows the visa type and consulate ratios, please ignore my typo in the chart.

.. image:: https://github.com/bwang40/CheckeeInfoCrawl/blob/master/image/consularandvisatype.PNG
   :height: 100

The following table indicate that Beijing consulate is actually not worst than any of the others. There are sayings that it is easier to get a visa at a embassy of a third country,but it is not really true from the data. 

.. image:: https://github.com/bwang40/CheckeeInfoCrawl/blob/master/image/consularrate.PNG
   :scale: 25

For those who are interested in Long checks, the following figure shows the histogram of the waiting days for long check cases (above 60 days) and all check cases. The histogram clearly shows that most cases get cleared with in 60 days. If you are unfortunate and went through the long check, there is another peak of visa approval on around 100 days. After that, the chance of being cleared dramatically reduced to almost zero. A very interesting observation is that, for those who get cleared within two weeks, the chance of getting cleared is almost the same on each of these 14 days.

.. image:: https://github.com/bwang40/CheckeeInfoCrawl/blob/master/image/hist.png
   :scale: 25

Disclaimer: 
=======================
This is only a project for acquiring data for desperate student under administrative processing like me to review. This is not for profit, but if you need me to withdraw it from github, Please contact me @ bwang40@hawk.iit.edu. Thank you so much.

Note: 
=======================
Warning: the code is written in python3 within less than 6 hours (Have to learn how to crawl information online first), it is incomplete and difficult to read. Use at your own risk. It get the work down for me. If you need to download the data I created, it is attached in `Final03-11-2019_16-29.txt <https://github.com/bwang40/CheckeeInfoCrawl/blob/master/Final03-11-2019_16-29.txt>`_. The file is loaded with data using pickle (python lib), you can restore it into python list using the following code
::
   with open("Final03-11-2019_16-29.txt", 'rb') as fp:
       APPLICATIONS_OF_ALL=pickle.load(fp)
Enjoy!
