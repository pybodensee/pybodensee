---
title: How to Choose a Python Package for Your Next Project?
create_date: 2024-06-13::00:00
author: Faisal Shahzad
status: published
categories: intermediate, tutorials
banner: incomplete
feature_image: fatureimage.png
description: Doing requirement analysis before choosing a Python Package for Your Next Project is necessary and can save you a huge hassle afterward.

---

Would you include a third-party Python package in your software package or Python package without analyzing it against certain benchmarks? Have you done your requirement analysis before executing `pip install next-big-package` or included a new dependency to your `requirement.txt` file? 

A benchmark or a requirement analysis ensures that the Python package you choose meets certain standards or requirements to meet the future needs of your project(s).


## Requirement Analysis

Performing a requirements analysis before selecting a Python package for your next project is necessary and can save you trouble later. When analyzing requirements, it's important to be critical and ask several questions about your project and libraries to be included in your project upfront.

- Which Python Version do you want to support?
- Which Operating System do you want to support?
- Do you need that full package or a small subset?
- Do you need a pure Python implementation or a wrapper around another package?
- Are you developing commercial or open-source applications?
- With which license you are going to distribute the new package?


## Wangener Benchmark (Version 1.0-Beta)

Our discussion during the [3rd PyBodensee Meetup](/meetups/meetup-3-python-code-organization/) on 02.07.2024 in Wangen im Allgäu, Germany, ended with the following points to consider before choosing a 3rd party Python package for your application. We call this approach the **Wangen Benchmark**, and it consists of the following.

This benchmark is bidirectional i.e. At each step it will check not only the package you want to include in your app but also your own app against it.

### 1. Applicability

Software and/or app **applicability** is an important factor for deciding the dependencies for a software project. Adding any 3rd party packages to your software will add some restrictions such as

- You can only distribute software under certain licenses.
- You can only include certain features.
- You need to buy an additional license for included packages.
- You have to open-source your software.
- Many others

To avoid any such restriction, you need to ask yourself some questions. 

**Do you need it for personal/internal company use or do you want to distribute it?**

If you need that 3rd party package for personal or internal business use then you do not need to disclose the source code of your app. For this case, adding additional libraries does not impose restrictions on you.  

**Do you want to distribute it as an Open-source or closed-source application?**

If you want to distribute a compiled version of your application, then the license of a 3rd party library can encourage you to adopt a certain license. A good example is Python libraries for QT Framework i.e. PyQt and PySide. PySide allows you to sell a compiled version of your application without adding additional restrictions. However, if you use PyQt, then you need to distribute your source code with a GPL3 license. 

**Is your project a pure Python application or includes remnants from Rust, C++, etc?**

If a 3rd party Python Package includes code from RUST, C, C++, or any other programming language then you can face additional restrictions on the distribution of your application. You might also have to compile those remnants by yourself. 

If you include a compiled version of those libraries, then you need to make sure that it is compatible with different hardware architectures e.g. if you need to distribute your app., action for Atom, ARM, or X86 platforms.

**Do you want to include a 3rd Party library as your dependency?**
In some use cases, 3rd part Python packages are included as submodules. This approach is used for such packages where long-term support is required (e.g. PyQtgraph) or in restricted environments where installing additional Python packages might not be possible/allowed (e.g. Ubuntu Touch is readable OS and restricts additional Python package installations). 

Including a Python package as a submodule can put some restrictions since you will be distributing their code under your license. If you have incompatible licensing issues, then it is recommended to use the ``requirements.txt`` file.

### 2. Versatility

The versatility of a 3rd party package is also very important. How many of your tasks can be done with a single library. Can you avoid installing multiple libraries instead of a single Python library?

If you are using only a small function is required which you can look into the source code of the repo and copy it there (please follow the license of that library). You do not need to make a dependency on a full library. 

### 3. Availability

Is this new third-party package available on multiple channels e.g. PyPi, Conda? If not then how you will keep including this package for future releases. 
Also ask yourself, how do you want to distribute your own package or softer? Is it close source or do you want to make it open source and distribute via Conda and Pip or your own download server?

### 4. Scalability

Do you want to scale up your app? Is this package suitable for scaling? 
Eg. If you are crawling online resources and your software or 3rd party package can crawl sinuously. The thesis is one example but maybe you want to process images at scale and PIL/Pillow might not scale up with your requirements. Will it be possible to switch to Opencv?
How difficult it would be to replace the package. Think about PyQt and PySide projects. It's generally not difficult to replace one with another whereas PIL to OpenCV would be problematic.

### 5. Popularity

You can look into code repositories e.g. on GitHub or GitLab and check their reputation. Pay attention to the following.

- How old is this repository?
- Is it a man's show?
- Look into PyPi download statistics for usage statistics.
- Who is maintaining
 - Country of origin. Is it from OpenSource friendly country e.g. Germany?
 - Is it a university project (PhD Project or a long-term project)
 - Is there any company behind this project and where are they based (EU or US Company)

Answers to the above questions should help you identify if the library is popular enough to be used in your project. Try to use those libraries that have a long maintenance history, and originate from Open Source friendly parts of the world. 

### 6. Stability

If stability is highly important for your application, then look into the following.

- Performance benchmarks and how good are the results
- What is the release cycle of this library?`
- What is a bug-fix approach? How long does a bug stay open?
- How is support working

Mature projects don't have a monthly release cycle. they might release the software over a yearly cycle. 
    

### 7. Dependability

Make sure that the Python package you are going to include in your app does not have any unwanted further dependencies. This can bloat your own package and other people might avoid your software at all.

Be careful when a project is supported by a VC-funded startup. If the VC fund pulls the breaks then those software might get abounded as well. A good example is synergy. GitHub is full of such packages VC leaves the company in between because this software was burning money and it was not possible to get profit out of it.

If your app has a dependency on any other third-party package then you will need a compile the version of the library to work properly e.g. installation opencv numpy, or scipy on Linux, Windows, and Arm64 will require different wheel files when you want to deploy your system to any subsystem.

Code scanning, for serious apps, makes sure that the package code base is not doing any suspicious things. Read the code, look into tests, and test against your own examples if you find anything suspicious. 

This becomes more critical if the package includes any dlls or executables making it hard to debug. Python packages e.g. Numpy or Scipy also include compiled versions of their packages with complete source code available and are generally safe to use.

However, any new library or relatively less popular library should be taken with a grain of salt. 

## Conclusion

Becoming dependent on some random package can be a long-term problem. Make sure you conduct proper requirements analysis before depending on a package because once your application starts maturing and delivering, it becomes difficult to drop or get rid of a dependency, and you want to avoid that situation.