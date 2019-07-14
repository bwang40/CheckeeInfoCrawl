
********************************************************
CheckeeInfo data Crawl and Analysis with Python 3
********************************************************

.. contents:: Table of Contents
   :depth: 2
   
Introduction 
=======================
On the 93rd day after my F1 VISA renewal application is under administrative processing. I decided to create this project to crawl the data on the checkee.info website. I am waiting for my VISA to get processed for over three months. Life is so miserable while waiting. Hopefully this situation is going to get better in the future.

In the beginning, I decided to use python class to define each application. However I end up use list of list to contain all the data. This is simply because I think it is more efficient for simple application like this. I can operate the list freely without concenring too much about memory issue.

The code is written in python 3 using the Jupyter of ANACONDA. (Easy to setup, all the libraries are loaded with the original ANACONDA)

Simply open the file  `CheckeeCrawl.ipynb <https://github.com/bwang40/CheckeeInfoCrawl/blob/master/CheckeeCrawl.ipynb>`_ with jupyter 

Driven by curiosity, I run the program again to view the status of the checked cases for visa. I found that we are not experiencing the worst case scenario. Indeed that the checked cases and long check cases are increased over 201912-201902. However compare to some other times, it is still a very small peak on the graph. 

Some Example Output
=======================
.. image:: https://github.com/bwang40/CheckeeInfoCrawl/blob/master/image/WeChat%20Image_20190312050230.png
   :scale: 25
   
.. image:: https://github.com/bwang40/CheckeeInfoCrawl/blob/master/image/checkAVGbymonth.PNG
   :scale: 25
   
.. image:: https://github.com/bwang40/CheckeeInfoCrawl/blob/master/image/consular.PNG
   :width: 10px
   
.. image:: https://github.com/bwang40/CheckeeInfoCrawl/blob/master/image/visatype.PNG
   :width: 10px
   
.. image:: https://github.com/bwang40/CheckeeInfoCrawl/blob/master/image/consularrate.PNG
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
