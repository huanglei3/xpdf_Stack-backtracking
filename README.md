xpdf v4.04

$ gdb --args pdftotext /home/fuzz/fuzzing_xpdf/out/default/crashes/id:000005,sig:11,src:002206,time:844503,execs:314684,op:havoc,rep:4

pwndbg> r
Syntax Error (2716): Illegal character ')'
Syntax Error: Couldn't read xref table
Syntax Warning: PDF file is damaged - attempting to reconstruct xref table...
Syntax Error (215): Dictionary key must be a name object
Syntax Error (238): Illegal character '>'
Syntax Error (245): Dictionary key must be a name object
Syntax Error (1525): Illegal character <6d> in hex string
Syntax Error (1526): Illegal character <6f> in hex string
Syntax Error (1527): Illegal character <72> in hex string
Syntax Error (1530): Illegal character <74> in hex string
Syntax Error (1532): Illegal character <78> in hex string
Syntax Error (1533): Illegal character <74> in hex string
Syntax Error (1534): Illegal character <2e> in hex string
Syntax Error (1537): Illegal character <6e> in hex string
Syntax Error (1540): Illegal character <6d> in hex string
Syntax Error (1541): Illegal character <3c> in hex string
Syntax Error (1544): Illegal character <2f> in hex string
Syntax Error (1545): Illegal character <54> in hex string
Syntax Error (1546): Illegal character <79> in hex string
Syntax Error (1547): Illegal character <70> in hex string
Syntax Error (1550): Illegal character <2f> in hex string
Syntax Error (1551): Illegal character <50> in hex string
Syntax Error (1553): Illegal character <67> in hex string
Syntax Error (1557): Illegal character <2f> in hex string
Syntax Error (1558): Illegal character <50> in hex string
Syntax Error (1560): Illegal character <72> in hex string
Syntax Error (1562): Illegal character <6e> in hex string
Syntax Error (1563): Illegal character <74> in hex string
Syntax Error (1569): Illegal character <52> in hex string
Syntax Error (1572): Illegal character <2f> in hex string
Syntax Error (1573): Illegal character <52> in hex string
Syntax Error (1575): Illegal character <73> in hex string
Syntax Error (1576): Illegal character <6f> in hex string
Syntax Error (1577): Illegal character <75> in hex string
Syntax Error (1578): Illegal character <72> in hex string
Syntax Error (1581): Illegal character <73> in hex string
Syntax Error (1583): Illegal character <3c> in hex string
Syntax Error (1584): Illegal character <3c> in hex string
Syntax Error (1587): Illegal character <2f> in hex string
Syntax Error (1589): Illegal character <6f> in hex string
Syntax Error (1590): Illegal character <6e> in hex string
Syntax Error (1591): Illegal character <74> in hex string
Syntax Error (1593): Illegal character <3c> in hex string
Syntax Error (1594): Illegal character <3c> in hex string
Syntax Error (1597): Illegal character <2f> in hex string
Syntax Error (1605): Illegal character <52> in hex string
Syntax Error (1610): Illegal character '>'
Syntax Error: Unterminated string
Syntax Error: End of file inside dictionary
Syntax Error: End of file inside array
Syntax Error: End of file inside dictionary
Syntax Error: End of file inside dictionary
Syntax Error: End of file inside dictionary
Syntax Error (140): Illegal character '>'
Syntax Error (148): Dictionary key must be a name object
Syntax Error (153): Dictionary key must be a name object
Syntax Error (155): Dictionary key must be a name object
Syntax Error (159): Dictionary key must be a name object
Syntax Error (163): Dictionary key must be a name object
Syntax Error (170): Dictionary key must be a name object
Syntax Error (215): Dictionary key must be a name object
Syntax Error (238): Illegal character '>'
Syntax Error (245): Dictionary key must be a name object
Syntax Error (1525): Illegal character <6d> in hex string
Syntax Error (1526): Illegal character <6f> in hex string
Syntax Error (1527): Illegal character <72> in hex string
Syntax Error (1530): Illegal character <74> in hex string
Syntax Error (1532): Illegal character <78> in hex string
Syntax Error (1533): Illegal character <74> in hex string
Syntax Error (1534): Illegal character <2e> in hex string
Syntax Error (1537): Illegal character <6e> in hex string
Syntax Error (1540): Illegal character <6d> in hex string
Syntax Error (1541): Illegal character <3c> in hex string
Syntax Error (1544): Illegal character <2f> in hex string
Syntax Error (1545): Illegal character <54> in hex string
Syntax Error (1546): Illegal character <79> in hex string
Syntax Error (1547): Illegal character <70> in hex string
Syntax Error (1550): Illegal character <2f> in hex string
Syntax Error (1551): Illegal character <50> in hex string
Syntax Error (1553): Illegal character <67> in hex string
Syntax Error (1557): Illegal character <2f> in hex string
Syntax Error (1558): Illegal character <50> in hex string
Syntax Error (1560): Illegal character <72> in hex string
Syntax Error (1562): Illegal character <6e> in hex string
Syntax Error (1563): Illegal character <74> in hex string
Syntax Error (1569): Illegal character <52> in hex string
Syntax Error (1572): Illegal character <2f> in hex string
Syntax Error (1573): Illegal character <52> in hex string
Syntax Error (1575): Illegal character <73> in hex string
Syntax Error (1576): Illegal character <6f> in hex string
Syntax Error (1577): Illegal character <75> in hex string
Syntax Error (1578): Illegal character <72> in hex string
Syntax Error (1581): Illegal character <73> in hex string
Syntax Error (1583): Illegal character <3c> in hex string
Syntax Error (1584): Illegal character <3c> in hex string
Syntax Error (1587): Illegal character <2f> in hex string
Syntax Error (1589): Illegal character <6f> in hex string
Syntax Error (1590): Illegal character <6e> in hex string
Syntax Error (1591): Illegal character <74> in hex string
Syntax Error (1593): Illegal character <3c> in hex string
Syntax Error (1594): Illegal character <3c> in hex string
Syntax Error (1597): Illegal character <2f> in hex string
Syntax Error (1605): Illegal character <52> in hex string
Syntax Error (1610): Illegal character '>'
Syntax Error: Unterminated string
Syntax Error: End of file inside dictionary
Syntax Error: End of file inside array
Syntax Error: End of file inside dictionary
Syntax Error: End of file inside dictionary
Syntax Error: End of file inside dictionary

Program received signal SIGSEGV, Segmentation fault.

pwndbg> bt
#0  0x000055555582b9bb in XRef::fetch (this=0x555555b83020, num=4, gen=0, obj=0x7fffff7ff0b0, recursion=0) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/XRef.cc:1182
#1  0x00005555556754a0 in Object::arrayGet (this=0x7fffff7ff0a0, recursion=0, obj=0x7fffff7ff0b0, i=0) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Object.h:243
#2  Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:566
#3  0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#4  0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#5  0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#6  0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#7  0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#8  0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#9  0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#10 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#11 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#12 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#13 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#14 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#15 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#16 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#17 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#18 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#19 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#20 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#21 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#22 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#23 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#24 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#25 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#26 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#27 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#28 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#29 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#30 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
#31 0x00005555556754d3 in Catalog::countPageTree (this=0x555555b85290, pagesObj=<optimized out>) at /home/fuzz/fuzzing_xpdf/xpdf-4.04/xpdf/Catalog.cc:567
