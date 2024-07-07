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

Would you include a third-party Python package in your software package or Python package without analyzing it against certain benchmarks? Have you done your requirement analysis before executing `pip install next-big-package` or included a new dependency to your `requirement.txt` file? 

A benchmark or a requirement analysis ensures that the Python package you choose meets certain standards or requirements to meet the future needs of your project(s).


## Requirement Analysis

Performing a requirements analysis before selecting a Python package for your next project is necessary and can save you trouble later. When analyzing requirements, it's important to be critical and ask several questions about your project and libaries to be included in your project upfront.

1. Which Python Version do you want to support?
2. Which Operating System you want to support?
3. Do you need that full package or a small subsets of it?
4. Do you need a pure python implementation or a python wrapper around another package?
5. Are you developing commercial or open-source applications?
6. With which license you are going to distribute the new package?


## Wangener Benchmark (Version 1.0-Beta)

Our discussion during the [3rd PyBodensee Meetup](/meetups/meetup-3-python-code-organization/) on 02.07.2024 in Wangen im Allgäu, Germany, ended with the following points to consider before choosing a 3rd party Python package for your application. We call this approach the **Wangen Benchmark**, and it consists of the followings.

This benchmark is bidirectional i.e. At each step it will check not only the package which you want to include in your app but also your own app against it.

### Applicability
Software and/or app **applicablity** is an important factor for deciding the dependencies for a software project. Adding any 3rd party packages to your software will add some restrictions such as

- You can only distribute software under certain license.
- You can only include certain features.
- You need to buy additional licese for included packages.
- You have to open source your sfotware.
- Many others

In order to avoid any such restriction, you need to ask yourself some questions. 

**Do you need it for personal/internal company use or do you want to distribute it?**

If you need that 3rd party package for personal or internal business use then you do not need to disclose the source code of you app. For this case, adding additional libraries do not pur restriction on you.  

**Do you want to distribute it as Open-source or closed source application?**
If you want to distribute a compiled version of your application, then the license of a 3rd party library can stress you to adopt to a certain license. A good example is Python libraries for QT Frame work i.e. PyQt and PySide. PySide allows you to sell a compiled version of your application without adding additionl restrictions whereas if you use PyQt, then you need to distrbuted your soursce code with GPL3 license. 

**Is your project pure python application or includes remnants from Rust, C++ or etc?**

If a 3rd party Python Package includes code from RUST, C, C++ or any other programming language then you can face additionl restirion on distribution of you appliction. You might also have to compile that remamnts by yourself. 

If you include a compile version of those libraries, then you need to make sure that it is compatible with differnt hardware architecture e.g. if you need to distribute your app.,ication for Atom, ARM or X86 platforms.

**Do you want to include a 3rd Party library as your dependency?**
In some usecase, 3rd part python packages are included as submodule. This approach is used for such packages where longterm support reuqired (e.g. PyQtgraph) or in restricted environments where installing additional python pckages might not be possible/allowed (e.g. Ubuntu Touch is readable OS and restricts additional Python package instllations). 

Including a python package as submodule can put some restrictions since you will be distributing their code under your license. If you have a incompatible licnesing issues, then it is recommended to use ``requirements.txt`` file.

### Versatility

Verstality of a 3rd party package is also very imporant. How many of your taks can be done with a single library. Can you avoid installing multiple libraries in leu of a single python library?

If you are using only a small function is require which you can look into the source code of the repo and copy it there (please follow the license of that library). You do not need to make a dependency on a full library. 

### Availability

Is available on multiple channels e.g. PyPi, Conda?
How to you want to distribute your own package or stofater. Is it close source or do you want to make it open source and distribute via Conda and Pip. Or your own download server.


### Licensibility
e.g. Camera drivers
Are commercial companies using the package and then selling support for ti.
Make sure you understand the license and its conseque4nes on your final product.
What is the license of your own application? Does it comply with all the included packages? Or do the user need to download it and install it bythemself. 

### Scalability

Do you want to scale up your app? Is this package suitable for scaling? 
Eg. If you are crawling online resources and does your software or 3rd party package is able to crawl asznnously. Thesis one example but mz be you want to process images at scale and PIL/Pillow might not scale up with your requirements. Will it be possible to switch to Opencv?
How difficult it would be to replace the package. Think about PyQt and PySide project. Its general not difficult to replace one with other whereas PIL to OPENCV would be problematics.


### Popularity

Github Reputation
How old
Is it one man show?
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
Make sure that the python package you are going to include in your app donot have any unwanted further depencies. This can bloat your own package and other people might avoid your software at all.

Becareful when a projects is supported by a VC funded startup. If VC fund pulls the breaks then those software might get abunded as well. A good example is synergy. GitHub is full of such packages VC leaves the company in bewtween befacsue theese software were burning money and it was not possible to get profit out of it.

If your app has a dependency on anyother third party package then you will need a compile the version of the libray to work properly e.g. for installatig opencv or numpy, or scipy on Linux, Windows and Arm64 will require different wheel files when you want to deploy your system to any sub system.

Code scanning, for serious apps, make sure that the package code base is not doing any suspicions things. Read the code, look into tests and test against your own examples if you found untying suspicious. 

This becomes more critical if the package is including any dlls or executables making it hard to debug. Python packages e.g. Numpy or Scipy also include compiled version of their packages with complete soiuyrce code available and are generally save to use.

However, any new library or relatively less popular library should be taken withy the grain of salt. 

## Conclusion

Becoming dependent on some random package can be a longterm problem. Make sure you conduct proper requiremetnt analysis before depending a package becuase once your application starts maturing and delivering, it becomes difficult to drop or get rid of a dependency, and you want to avoid that situation.