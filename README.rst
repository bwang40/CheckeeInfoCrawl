
********************************************************
CheckeeInfo data Crawl and Analysis with Python 3
********************************************************

.. contents:: Table of Contents
   :depth: 2
   
Introduction 
=======================
On the 93rd day after my F1 VISA renewal application is under administrative processing. I decided to create this project to crawl the data
on the checkee.info website. I am waiting for my VISA to get processed for over three months. Life is so miserable while waiting. Hopefully
this situation is going to get better in the future.

Note: 
=======================
Warning: the code is written in python3 within less than 6 hours (Have to learn how to crawl information online first), it is incomplete
and difficult to read. Use at your own risk. It get the work down for me. If you need to download the data I created, it is attached in
Final03-11-2019_16-29.txt. The data is loaded with data using pickle (python lib), you can restore it into python list using the following
code::
with open("Final03-11-2019_16-29.txt", 'rb') as fp:
    APPLICATIONS_OF_ALL=pickle.load(fp)
Enjoy!
