---
layout: post
title: First Post
---

The first project assignment for Data Science Bootcamp was a group project named Project Benson. My project team included Kelly Nelson and Fahad Sami. 

The project involved a fictional organization named WomenTechWomenYes (WTWY).

**Overview**

WTWY, a non-profit organization based in New York City, has their annual gala the first week of June each year. The goal of the gala is to fill their event space with individuals passionate about increasing the participation of women in technology, and to concurrently build awareness and reach. To this end they deploy volunteer street teams at entrances to subway stations. The street teams collect email addresses and those who sign up are sent free tickets to the gala.

The goal of this project is to utilize publicly available data to develop a recommendation for WTWY on where and when to deploy their street teams in order to maximize the collection of email addresses from individuals who are likely to attend the gala and contribute to the cause.

**Key Assumptions**

The first two assumptions are related to how we identified our target audience…proxies for interest in technology and willingness to contribute  
•	Individuals who live or work in areas with a greater density of technology companies will have a higher propensity to engage and participate in technology related causes  
•	Individuals who live in areas with higher donor penetration will have a higher propensity to engage and contribute to charitable causes 

The next assumption is related to how we refined the target selection to optimize the deployment of our street teams  
•	Higher MTA station volume within the target geography will correlate with greater street team effectiveness  

The final assumptions are related to timing and available resources  
•	A dozen street team members, working in pairs, are available for deployment at any given time  
•	Deploy street teams in April 2019 based on the required lead time for the gala scheduled the first week of June 2019  
•	April 2018 MTA turnstile data is representative of expected station volume during April 2019 street team deployment   

**Data Sources**

*Technology Data*  
•	Used BeautifulSoup to scrape company name information from The Hitchhiker’s Guide to New York City Tech website  
•	The data URL is: http://startupguide.nyc/  
•	Used Google Maps Places to pull the address information which was parsed for the zip codes associated with each of the company’s NYC location  

*Donor Data*  
•	Individual Income Tax Statistics by zip code are publicly available on the IRS.gov website  
•	The available data includes selected income and tax items classified by State, Zip code, and AGI (adjusted gross income)  
•	The most recent year available is 2015  
•	The subset of data that was used in this analysis includes the following:  
	  - Zip code (ZIPCODE)  
	  - Total number of returns (N02650)  
	  - Total income amount (A02650)  
	  - Number of returns with contributions (N19700)  
	  - Contributions amount (A19700)  
•	This data is available for individuals who itemize on their federal tax returns (approximately 30% of all returns)   
•	The data URL is: https://www.irs.gov/pub/irs-soi/15zpallagi.csv  
•	The documentation URL is: https://www.irs.gov/pub/irs-soi/15zpdoc.doc  

*MTA Data*  
•	2018 MTA Turnstile data included weeks ending April 7th, April 14th, April 21st and April 28th  
•	Cumulative turnstile entries per day for each Control Area, Unit, SCP, Station  
•	372 total stations included in dataset  
•	The data URL is: http://web.mta.info/developers/data/nyct/turnstile/turnstile_{}.txt  

**Analysis**

Technology company penetration by zip code  
•	Identified 8 (of 26) zip codes where 5 or more technology companies are located  

Donor penetration by zip code  
•	Identified 33 (of 131) zip codes where the percentage of individuals claiming charitable deductions was greater than 38%  

Combined Donor penetration and Technology company density resulted in the following 6 zip codes in our final target geography:  
•	22 MTA stations located within 6 target zip codes  
•	Union Square and Penn Station have highest traffic  
•	Traffic peaks after 5pm for both stations  

**Recommendations**  

•	Divide the resources between the two stations   
•	Deploy on Wednesday and Thursdays during the evening commute  
•	We estimate we will reach  
	  - ~40k people / hour between 5-9pm in Union Square   
	  - ~60k people / hour between 6-8pm in Penn Station  

**Additional Resource Consideration**  

•	Transportation Hub  
	  - Connects NJ Path,123, 456, and Brooklyn  
	  - Third highest foot traffic overall, when combined  
	  - Set up table in oculus shopping center  
•	Fulton Center:  
	  - Donor percent = 33.7%, 2 tech companies  
•	WTC PATH:  
	  - Donor percent = 43.8%, zero tech companies  

 

