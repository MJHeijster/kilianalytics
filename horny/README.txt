-------------------------------------------------------------------------
-- mIRCStats v1.25 beta, released 6th of October 2015                  --
-- by Mikko 'Ave' Auvinen                                              --
--                                                                     --
-- Email: mircstats (o) nic.fi                                         --
--        (When emailing me, include word 'mircstats' in subject line  --
--         to make it pass my spam filter easier.)                     --  
--                                                                     --
-- homepage: http://www.mircstats.net/                                 --
--       or  http://www.nic.fi/~mauvinen/mircstats/                    --
-------------------------------------------------------------------------

FTP and HTTP-Components are programmed by Francois Piette 
( http://www.overbyte.be/frame_index.html ).
  - mIRCStats occasinally checks for a "New version" message from www.nic.fi 
    web server. This uses HTTP GET method, and doesn't send any information 
    out. If a new mIRCStats version is available, a message window pops up.
    
TPNGImage component used by mIRCStats Pipe Lab was done by Gustavo Daud.
( http://pngdelphi.sourceforge.net/ )

-------------------------------------------------------------------------


mIRCStats is a log analyzer originally developed for analyzing IRC channel log files and
later upgraded to understand any kinds of logs, for example any RSS feed contents can be
turned into statistics by using RSSLogger (http://rsslogger.mircstats.net). 

mIRCStats creates a nice looking HTML-page consisting of activity statistics, 
user reports, word and URL statistics, chat partners map and and all kinds of miscellaneous 
information collected from the log files.

All texts in mIRCStats-generated stats pages are fully configurable through language
files (located in Language sub-directory). mIRCStats can also read nearly every possible 
log file format because the log parser can be configured with parser configuration files 
(located in Parser sub-directory).


================================================
See versionhistory.txt for full list of features
================================================


Some guidelines:
----------------

Getting help:

	Pressing F1 while running mIRCStats opens the On-line help.
	Use index and search to find the subject you're looking for.
    
    IMPORTANT: mIRCStats help file not displaying properly?
      Windows might need you to set the help file as "trusted".
      Here's how you can do it:
        1) Go to mIRCStats installation directory
        2) Right-click mIRCStats help file (mircstats.chm) and choose Properties
        3) On the General tab, click the button labeled "Unblock"
        4) Click OK and re-open the help file.
      After this operation the help file should show pages properly.
    		
	Or visit mIRCStats Forums at http://forum.mircstats.net/
    

How to configure your mIRC to log your channels:

	* Make sure you have a mIRC client program 
	  (download: http://www.mirc.co.uk) 

 	* In mIRC Options/IRC/Logging settings page:
	  - Turn on "Automatically log channels" 	  
    	  - Check (=turn on) "Strip codes"
	  - Check "Timestamp logs" (Adds timestamp to logs even if you don't use them in channel windows)
	  - Uncheck "Lock log files" (This lets mIRCStats analyze logs while mIRC is active)

	  - Uncheck "Show mode prefix" at Options/Irc page

	After doing this your mIRC is making .log-files of all channel activities on those channels
	you are on. 


How to create statistics based on RSS or Atom feed contents:

    * Download RSSLogger from http://rsslogger.mircstats.net
	
	* Open RSSLogger help to see detailed help
	
	* When analyzing RSSLogger-created logfiles with mIRCStats, select parser configuration file
	  as RSSLogger_parser.txt and language file as lang_RSSLogger_english.msl
	  
	
How to use mIRCStats with other log formats:

	You need to adjust the mIRCStats log parser to understand the format used in your log files. 
	This can be done by selecting a proper Parser Configuration File (At "Log parser" settings page 
	in mIRCStats). Parser Configuration Files done by other users can be downloaded from Parser 
	Configuration File download site: http://www.mircstats.net/parser/
	
	If you cannot find a Parser Configuration File that matches your logging format, you can easily
	create one by yourself. Check Config/mIRC_parser.txt for an example how default parser rules were
	defined.
	
	You can find more info from mIRCStats help file (Press F1 in mIRCStats).
		
	
Generating your first stats page from your logs.
	
	You can generate statistics by running mIRCStats and selecting the log file that you want to analyze.
	Selection of multiple log files can be done by defining a filter like "c:\logs\mychannel_*.log" .
	User interface should be easy to understand, but in case you need assistance,
	press F1 to open the help file where you find information for most problems.


Basic information how to publish your stats in the internet:
	
	* Stats pages are created by default to /html directory under your mircstats dir.
        - You can configure the built-in ftp client to upload stats files to your web server
          (See File Transfer page in mIRCStats, press F1 on that page for help).
        - or use any other file transfer software to upload the generated files
          (html, css, gif and jpg) to some directory ("stats" for example) at your web server.

	* Advertise the stats page URL to friends at your irc channel.
        - You can configure mIRCStats to do this with DDE Messaging. See "DDE Messaging"
          settings page.


Automating your stats updates:

	There's several ways to automate mIRCStats. 
	Open the help file (F1) and go to "Inside mIRCStats -> Ways to automate your stats updates"


	
mIRCStats accepts following command line parameters:

	mircstats.exe [-l logfile] [-h htmlfile] [-c configfile] [-req request_name]
	
	[ ] means the parameter is optional, you shouldn't write []-characters around parameters.
	If your filenames or paths include spaces, surround names with "quotes".
	
	You can load multiple config files by specifying more "-c configfile" parameters.
	Always load the most generic config file first, and after those more specific ones.
	(Like this: -cfg mysettings.cfg -cfg mycustomstats.cust.cfg -cfg chinese.lang.cfg)


mIRCStats is a SHAREWARE program
	
	If you like to use mIRCStats, please register it. By doing that you also support 
	development of new features, which you can take full advantage of when registered!
	
	Take a look at http://www.mircstats.net/register.html or register.txt for further info.


Version info

	See file versionhistory.txt for full list of features



Limitations:

- Maximum number of days to be analyzed with a single scan...........NO LIMIT
- Maximum number of lines per day to be saved to channel history...... 262140
- Maximum number of days in channel history......................... NO LIMIT
- Maximum number of nicks in one scan............................... NO LIMIT
- Maximum number of words in word stats............................. NO LIMIT
- Most variables are limited by range of signed 32-bit integer.... 2147483647
  
Parser-limitations:
- Every log has to have some line with date (in some format). No lines are analyzed before that line.
- Nicknames can't contain spaces.


Thanks to:

* All registered users who believe that it can still be developed further
* mIRCStats beta tester group
* Helpful people at mIRCStats forums ( http://forum.mircstats.net )
* Language and Parser Configuration File writers from all around the world
* Everyone who has sent me mail and suggestions about mIRCStats


Please send bug reports and feature suggestions to mircstats (a) nic.fi



DISCLAIMER
==========

By using mIRCStats you are agreeing to the following terms:

1) mIRCStats is supplied as is.  The author disclaims all warranties, expressed or 
implied, including, without limitation, the warranties of merchantability and of 
fitness for any purpose. The author assumes no liability for damages, direct 
or consequential, which may result from the use of mIRCStats.

2) If you choose to register mIRCStats (purchase a registration code that unlocks 
all features of mIRCStats), you are responsible for maintaining the confidentiality 
of your registration code and are liable for any harm resulting from disclosing or 
allowing disclosure of your registration code.

3) Registration code is personal, you are not allowed to generate stats for 
other peoples' channels with features which require registration. This means 
that providing "stats service" is not allowed. Contact me by emailing at 
mircstats (o) nic.fi if you are planning to set up a service like that.


Copyright of mIRCStats is owned by Mikko Auvinen
