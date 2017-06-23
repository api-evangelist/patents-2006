---

title: Database heap management system with variable page size and fixed instruction set address resolution
abstract: A heap management system for a database uses “sets” of pages to store database information. As memory for each successive set of pages is allocated, more memory is allocated for storing rows in each page of the set. Similarly, the maximum number of rows of information storable in each page of each set is greater for each successive set of pages. The number of computer instructions needed to resolve (or calculate) the memory address for a particular row is fixed. Given a target row number, (and the number of rows in the first page, and the width of the column or column group), only a fixed number of computer instructions need to be executed to resolve the starting memory address for the target row. In addition, information of the same type (i.e., one or more columns of a table) may be stored in different pages, and these pages may be located in discontiguous memory segments. This allows space for new rows to be allocated, without requiring all pre-existing rows to be moved to a different memory segment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07818346&OS=07818346&RS=07818346
owner: Temporal Dynamics, Inc.
number: 07818346
owner_city: Fishers
owner_country: US
publication_date: 20060801
---
