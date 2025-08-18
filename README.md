# HP-41_NOVCHAP.ROM

[![HP-41](https://img.shields.io/badge/HP--41-Calculator-orange)](https://en.wikipedia.org/wiki/HP-41C)
[![Ruby](https://img.shields.io/badge/Ruby-CC342D?style=flat&logo=ruby&logoColor=white)](https://www.ruby-lang.org/)
[![License](https://img.shields.io/badge/License-Public%20Domain-brightgreen.svg)](https://unlicense.org/)
[![GitHub stars](https://img.shields.io/github/stars/isene/HP-41_NOVCHAP.ROM.svg)](https://github.com/isene/HP-41_NOVCHAP.ROM/stargazers)
[![Stay Amazing](https://img.shields.io/badge/Stay-Amazing-blue.svg)](https://isene.org)

An HP-41 rom enhancing the family of NoVRAM modules

## The NOV CHAP rom - version I
The NOV CHAP is an HP-41 companion module image to the physical NoV modules produced by Diego Diaz (http://www.clonix41.org). It greatly enhances the value of the NoV modules by adding several important features. NOV CHAP is created by Geir Isene and Ángel Martin. It is a continuation of Geir Isene's ICEBOX project (https://github.com/isene/hp-41_icebox) which in turn was a fork of Ángel Martin's Toolbox containing lots of utilities compiled from many sources.

The NOVCHAP is useful even if you don't use a NoV module as it contains many advanced Extended Memory functions and other neat utilities.

The NoV family of modules consists of the NoVRAM, The NoV-32 and the NoV-64.

The NoVRAM gives the user four 4K pages of HEPAX RAM (pages #8 - #B) and four 4K pages of burnable EPROM (pages #C - #F). The RAM pages are non-volatile and retain its content even when the module is removed from the calculator.

The NoV-32 adds a second block of four 4K HEPAX RAM pages (32K RAM total).  Whether you use the first block of 4x4K RAM or the second block is determined by the word contained at address 4100. If the word is hXX0, the first block is selected, while the word hXX1 selects the second block (the X's can be any value).

With the NoV-64, you get four blocks of 4x4K HEPAX RAM (64K RAM total) and an additional block of 4x4K of EPROM. The address containing the configuration word is still 4100, but now you can configure the module many ways. Please refer to the manual for details. Here it suffices to say that the first value in the word selects the ROM block to be used (pages #C- #F) with the value of 1 indicating the first ROM block and the value of 2 indicates the second ROM block. The last value of the word indicates which HEPAX RAM block to fill into pages #8 - #B (0-3). Entering h102 into the address 4100 tells the NoV-64 to use the first ROM block in pages #C - #F and the third HEPAX ram block in pages #8 - #B. If the first value is zero, no ROM block is selected for pages #C - #F. It is possible to use two RAM blocks and no ROM block. If you want such a configuration, then the first value must be zero and the last two values will indicate which RAM blocks to be used (largest value first); h031 would configure the fourth RAM block for pages #C - #F while the second RAM block would fill up pages #8 - #B.

The functions of the NOVCHAP is listed in XROM number sequence and explained with both function input and output. If you find anything unclear, or if you have suggestions for improvement - please contact me (g@isene.com).

There are several FOCAL programs in this module (marked in red font).  These programs are disguised as MCODE programs and can only be copied to RAM by setting the pointer within the program (such as GTO "FLSORT" and then do a "silent copying" with COPY ALPHA ALPHA. However this may result in an unstable RAM, so do this at your own risk. The functions come in four categories;

1. NoV specific functions
2. Advanced Hepax functions
3. Advanced Extended Memory functions
4. Utility functions

They are marked by separate headers in the module and different colors in this user manual.

Feel free to use the NOVCHAP.ROM or tweak it's source under the GPLv2 license.

The User Manual should contain what you need to make good use of the module.

## Extra MCODE tidbit: Using the HP-16C as a tool
Being a calculator collector and addict, I search out new uses for my little precious ones. My calculators are solutions in search of a problem.

I have always thought of the HP-16C as a special item in my collections. It's the only programmable programmers calculator, and it's capabilities are indeed impressive.  But other than simple additions and subtractions in hex mode, I didn't really find any use for it. Until I got more heavily involved in Machine CODE (MCODE) programming on the HP-41.

I really love MCODE. With it I can make the HP-41 do just about anything. It's a nice challenge to do weird stuff on a 30 year old technology.

Some of the challenges in MCODE has to do with calculating jump codes. I used to carry a set of tables to get the right hex words for jumping short distances, for doing calls to the operating system and for the port dependent jumps. No more. The HP-16C comes to the rescue.

Go to the ICEBOX page (https://github.com/isene/hp-41_icebox) for more information and for the program listing.

## License
This software is released into the Public Domain.

