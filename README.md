# CIS550-Project

## CIS 550 Project Milestone 1 - Project Outline

Group Members (Team 12)
- Steven Chang ()
- Yiheng Xiong (yihengx@seas.upenn.edu)
- Zhiqi Fu(zhiqifu@seas.upenn.edu)
- Yankai Liu() 	 		
			

### Motivation for the idea/description of the problem the application solves

Since all of our group members love music, we want to create a website that could help people who have the same interest as we do to quickly find quality music. They could not only search for a specific type of music, but also songs that gain lots of awards.
 							
List of features you will definitely implement in the application
1. Top N popular songs for a given genre and year are songs which have the highest weekly ranks and weeks on billboard chart
2. Most popular songs in a user-selected genre, and released before/after/during a certain year/time window are songs that have won both Grammy Awards and RIAA certifications during this certain time period
3.  Directly output all the artists who have won Grammy Awards or whose album(s) received RIAA certifications before, ordered by the number of awards they received on the ‘Artists’ page
【再补充一些】
 							
List of features you might implement in the application, given enough time
 							
### List of pages the application will have and a 1-2 sentence description of each page. (We expect that the functionality of each page will be meaningfully different than the functionality of the other pages).
1. Songs Page
2. Artists Page
3. Albums Page
Relational schema as an ER diagram
		
SQL DDL for creating the database
CREATE TABLE Artist (
    index INT(11),
    Artist VARCHAR(20),
    Followers INT(11),
    NumAlbums INT(11),
    YearFirstAblum INT(11),
    Genres VARCHAR(20),
    Gender VARCHAR(20),
    Group/Solo VARCHAR(20),
    PRIMARY KEY (Artist))


CREATE TABLE BBHot100 (
    index INT(11),
    Artist VARCHAR(20),
    Song VARCHAR(20),
    Peak INT(11),
    Rank INT(11),
    NumWeeks INT(11),
    Cur_Week DATETIME( ),
    Release_Date DATETIME(),
    WritingCredit VARCHAR(20),
    PRIMARY KEY (Artist)
    CONSTRAINT Artist REFERENCES Artist(Artist) )
【table没写完，还要补充一下】
【不确定时间的datatype是不是DATETIME】
			
### Explanation of how you will clean and pre-process the data. ​This tutorial demonstrates how to do simple pre-processing in Python.

1) Explode:
Since many features has more than 1 value(store as a list), I will use explode() function in Python to separate them
2) Null value/Useless features:
When the feature is not important or it contains lots of null value(for example, there is one column called “features” in spotifyWeeklyTop200. It has 82% null value and 17% ‘others’. It is apparent that we could not get any useful information from this feature. Therefore, we will remove this column.) 
3) Join Tables
Although GrammyAlbum and GrammySong are two separate table, they shared similar features. We will join these two tables together during data pre-processing. Same for RIAAAlbum and RIAASingle.

### List of technologies you will use. You must use some kind of SQL database. We recommend using MySQL specifically because you will use MySQL in HW2, and we will provide guidance for setting up a MySQL database.
 							


### Description of what each group member will be responsible for 
 							
						 					
				
			
		

