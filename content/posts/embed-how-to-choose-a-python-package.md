---
title: How to Choose a Python Package for Your Next Project?
create_date: 2024-06-13::00:00
author: Faisal Shahzad
status: draft
categories: intermediate, tutorials
banner: incomplete
feature_image: fatureimage.png
description: Doing requirement analysis before choosing a Python Package for Your Next Project is necessary and can save you a huge hassle afterward.

---

Will you include a 3rd Party Python package in your software package/library? Have you done your requirement analysis before executing `pip install next-big-library` or included a new dependency to your `requirement.txt` file? 

## Requirement Analysis

Doing requirement analysis before choosing a Python Package for Your Next Project is necessary and can save you hassle afterward. For requirement analysis, it is important to ask several questions beforehand.

1. Which Python Version do you want to support?
2. Which Operating System you want to support?
3. Do you need that full package or a small subsets of it?
4. Do you need a pure python implementation or a python wrapper around another library?
5. Are you developing commercial or open-source applications?
6. With which license you are going to distribute the new package?


Our discussion during the 3rd PyBodensee Meetup, concluded upon on the following points that one should consider before choosing a 3rd Party Python Package for your application. 

### Verstality
may be only a small function is require which you can look into the source code of the repo and copy it there (please take care of the license) 
or do you need other function from the library for any other parts of the applicaiotn.


### Scalability

Do you want to sell it?


### Replaceablity

### Popularity

Github Reputation
How old
Is it oneman show?
Who is maintaintg
    Couontry of origin (e.g. Lua from Brazil or Debian)
    uni (Phd PRoject or lonterm project)
    company (EU or Us Comapny)

### Stability

Performance benchmarks
What is the release cycele
Waht is bug fix approach
How is support working

Mature projects dont have monthly relase cycle. they might release the sfotware over several years. 
    

### Dependablity
do this package has further depencies which can bloat your own package and other people might avoid your software at all.
Becareful when a projects is supported by a VC funded startup. A good example is synergy . What ahppens if VC leaves the company inbewtween ebcaseu its not possible to get profit out of it.

Alos, . This will build a sort of dependency on anyother thirdparty library ad you will need a ompile version of the libray to work properly. E.g. for installatig opencv or numpy, or scipy on Linux, Windows and Arm64 will require different wheel files when you want to deploy your system to any sub system.


### Usability/Applicationality
Do you need it for personal/internal company use or do you want to distribute it?
Do you want to make it a submodule e.g. pyqtgraph? or should be installed seperately?
requiremtns.txt
submodule
e.g. Camera drivers
Is available on multiple channels e.g. PyPi, Conda?
Are commercial companies using the paakcage and then selling support for ti.

## Conclusion

Becoming dependent on some random library can be a longterm problem. Make sure you conduct proper requiremetnt analysis before depending a library becuase once your application starts maturing and delivering, it becomes difficult to drop or get rid of a dependency, and you want to avoid that situation.