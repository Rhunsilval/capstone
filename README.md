## **The Cost of Moving Food: Exploring Food Sustainabilty Through the Lens of Transport**
*Capstone Project for Part-Time Data Analytics Cohort #5 program at Nashville Software School.*

### **Contents**
- [Motivation](#Motivation)
- [Data Questions](#Data-Questions)
- [Known Issues and Challenges](#Known-Issues-and-Challenges)
- [Data Sources and Tools](#Data-Sources-and-Tools)
- [Schedule](#Schedule)
- [Approach Outline](#Approach-Outline)
- [Acknowledgements](#Acknowledgements)


**Considering sustainabilty in the choices we make is important, but it's often difficult to determine what the more sustainable choices are.** When deciding what to eat, or order, or prepare, there are a lot of factors to consider.  This project specifically examines some of the questions and data concerning how food is transported from a producer to a consumer, and what kind of sustainabilty issues are involved in that transportation.  What kind of transport is used to move the goods?  What kind of fuel does that transport use?  How much fuel is used?  How polluting is that fuel?  How expensive is that fuel?  And, how does transporting food over long distances compare to moving food over short distances in terms of sustainability?  Specifically, this project defines sustainabilty as being efficient in terms of delivery time, fuel consumption, and financial cost, while minimizing CO2 pollution.

### **Motivation**
"Food" is a subject of great interest and passion for me.  Not just in terms of trying new recipies or following foodie-trends, but I am also very curious about the topics of gastro-anthropology, the socio-ethics of food, accessibilty, and sustainability.  

In all the choices that I make in my personal life, especially with my food-related choices, I try to keep sustainability in mind.  Not only in terms of environmental sustainability, but also in terms of financial sustainability. I make a deliberate effort to make the best choices for myself that also minimize the negative effects those choices have on my community and my environment.

I was initially drawn towards this project's specific topic out of a pair of questions that I'd been curious about for a while.  

First, why are the strawberries sold in my grocery store, in the height of strawberry season, imported from California, when I know for a fact that they grow locally.  Is it really so much cheaper to move strawberries in from across the country than it is to bring them in from across town?

And, secondly, with "sustainability" such a hot topic right now (rather than just my own personal goal), why don't I see more of an effort to embrace and advertise sustainability in Nashville's restaurant scene?  There's a few restaurants in town that advertise themselves as sustainable, but not many.  And with Nashville being such a foodie town, and sustainability being such a trendy topic, this makes no sense to me.  

I've read articles about the subject for years, but I've always been curious about what the actual data looks like.  The training and skills I've learned with Nashville Software School, and the opportunity to assemble this project, have given me the chance to finally get to examine and analyze some of this data for myself.  

*Back to [Contents](#Contents)* 


### **Data Questions**
- How fast does cargo travel via different methods?
- How much fuel does it take to move cargo by these methods?
- How much CO2 is produced to move this cargo?
- How much is spent (USD) on fuel to move our food-centric cargo?


**How do I know which transport is carrying food, versus carrying something else, or carrying mixed cargo?**
Ultimately, in this project, I don't know.  
This project instead focuses on averages: what the impacts are of transporting 1-ton of general "dry goods".  This limitation does necessitate excluding the bulk transport of liquid food products, but not packaged versions of these products, nor the original format of those ingredients (livestock or produce).

By examining specifically the average effects of transport by weight, it matters less whether that vehicle is transporting 1-ton of apples or 1-ton of action figures.  The effect would be the same.

*Back to [Contents](#Contents)* 


### **Known Issues and Challenges**
**Variable Diversity Within the Scope of My Data Questions**
*Many of my questions center on how much fuel is consumed when moving cargo.  Answer varies depending on:*
- The kind of fuel
- The kind of vessel
- How much weight the vessel is carrying

*The answer can also vary depending on:*
- Age of the vehicle
- Urban congestion
- Weather
- Elevation
(My data did not specifically include the effects of these factors, but they admittedly would have an effect)


**Variable Diversity Within the Data Itself**
- Fuel measurements: some data offered fuel levels listed in tons, others in gallons.  And different fuels weigh different amounts
- Fuel consumption rates: some data provided the amounts of fuel consumed by the day, others by the hour, and others by distance
- Rates of speed: some data listed speed in kilometers-per-hour, some by miles-per-hour, and some by nautical knots
- Weight diversity: how much a shipping container weighs, or how much weight a transport vessel is carrying, varies significantly on a case-by-case basis


**My Methodology**
- Convert all speeds to miles per hour (MPH)
- Convert all fuel measurements to gallons
- Determine average weights for cargo loads, convert all weights to tons
	- Ships: ship size was provided in ranges of standard TEU measurements: Twenty-foot Equivalent Units (the standard size of a cargo container)
		- Maximum gross mass of dry goods per TEU is 52,910 lbs
		- I used the mean TEU capacity for each ship size category, then calculated shipment weight based upon the maximum TEU weight of that mean size
		- I dropped the largest ship size category from my dataset.  It was listed as "10,000+".  Without a maximum ceiling on that weight range, I could not accurately determine an average cargo weight
	- Planes: 
		- Via my research, I learened that cargo planes are almost always the same size and make as passenger planes
		- The most common plane (Boeing 737) carries an average weight of 45,000 lbs of cargo 
		*Smithsonian National Air and Space Museum
	- Trucks: 
		- My data concerning truck weights provided the maximum legal weight loads for shipping trucks, based on the old Class 1-8 truck classification system
		- My data concerning truck fuel consumption was provided using the new government 3-category truck classification system
		- To determine an average cargo load with the new system, I filtered the old 8-class system into the new 3-category system, then used the mean weight capacity of that new size range to determine a cargo weight
	-Trains:
		- Published research I found clearly stated that the average weight of a non-liquid cargo load was 30,000 tons
			-*Source 1 : [Factcheck](https://www.factcheck.org/2008/07/fuel-efficient-freight-trains/)
			-*Source 2 : [The Association of American Railroads](https://www.aar.org/data-center/)
- Filter all information through the lens of efficiency via a ton-mile
	- Calculated by multiplying how much weight a vessel is carrying by the MPG of that vessel

*Back to [Contents](#Contents)* 


### **Data Sources and Tools**
**Data Sources**
This project primarily used data published by the U.S. Government
- U.S. Surface Transportation Board: [Rail Service Data](https://www.stb.gov/reports-data/rail-service-data/)
- U.S. Department of Transportation: [Average Truck Speeds on Selected Interstate Highways: 2009](https://ops.fhwa.dot.gov/freight/freight_analysis/nat_freight_stats/docs/10factsfigures/table3_8.htm)
- U.S. Department of Energy: [Motor Vehicle Mileage, Fuel Consumption, and Fuel Economy](https://www.eia.gov/totalenergy/data/browser/?tbl=T01.08)
- U.S. Department of Energy: [Short-Term Energy Outlook, December 2021](https://www.eia.gov/outlooks/steo/tables/pdf/2tab.pdf)
- U.S. Department of Energy: [Carbon Dioxide Emissions Coefficients by Fuel](https://www.eia.gov/environment/emissions/co2_vol_mass.php)
- The Conservation Fund: [Moving Freight: Economy and Atmosphere](https://www.conservationfund.org/images/programs/files/CSX_Final-Curriculum.pdf)
- [The Geography of Transport Systems](https://transportgeography.org/contents/chapter4/transportation-and-energy/fuel-consumption-containerships/), by Jean-Paul Rodrigue 
- The National Air and Space Museum: [How Things Fly](https://airandspace.si.edu/exhibitions/how-things-fly)
- The Engineering Toolbox: [Combustion of Fuels- Carbon Dioxide Emission](https://www.eia.gov/environment/emissions/co2_vol_mass.php)

*Back to [Contents](#Contents)* 


**Tools**
- 'MS Excel', Microsoft Office Professional Plus 2019
- 'Jupyter Notebook', version 6.3.0
- 'GetData Graph Digitizer', version 2.26

*Back to [Contents](#Contents)* 


### **Schedule**
11/20/2021 ..... Get the data
12/02/2021 ..... Clean and explore the data, fill data gaps with research
12/11/2021 ..... Research correlations, create charts, presentation assembly and rehearsal
12/18/2021 ..... Internal Demos
01/06/2022 ..... Demo Day!

*Back to [Contents](#Contents)* 



### **Approach Outline**
To track progress and keep myself organized, I used a combination of the Project (Kanban) board in the GitHub repository, and a spreadsheet of sources links on Google Drive
- Find data for fuel consumption, for each transit type
- Find data for cargo weight loads, for each transit type
- Find data for types of fuel, for each transit type
- Find data for CO2 emissions, for each fuel type
- Find data for fuel prices, for each fuel type
- Clean and explore data, fill gaps in my data with additional research
- Convert all datasets to standard units: 
	- Fuel amounts to gallons
	- Cargo weights to tons
	- Fuel consumption to Miles-Per-Gallon
	- Speeds to Miles-Per-Hour (ground level)
- Determine speed and cargo-carrying averages for each transit type
- Explore my data questions, calculating and comparing different transportation methods all through the lens of a ton-mile
- Determine the best method for merging my datasets
- Create and edit charts and graphs that clearly explain the findings within my complicated data.  My aim was simplicity so as not to confuse or overwhelm my audience
- Determine the narrative of my presentation, and assemble my presentation
- Practice my presentation, with a stopwatch, to multiple test audiences.  Condense and make edits

*Back to [Contents](#Contents)* 


### **Acknowledgements**
First and foremost, I need to offer my deep and sincere thanks and gratitude to my instructors and to the staff at **Nashville Software School.**  With their support and knowledge, I have felt thoroughly empowered and equipped to tackle the complicated and daunting task of learning an entirely new skill set and facilitate a new career shift.

- Specific thanks go out to my instructors - the ever-patient-and-knowlegeable **Andrew Marsee**, the always-encouraging-and-helpful **Teresa Whitesell**, and the helpfully-analytical-and-good-humored **Amanda Partlow**.
- They are invaluable as instructors and an assett to the **Nashville Software School**.  Knowledgeable.  Able and willing to answer 1001 questions - often on the fly and often outside of regular class hours.  And very helpful in helping me to both learn these programs and learn how to research to find answers to my questions.

Secondly, a shout-out to **my fantastic classmates**!  Not only were you a ton of fun to learn alongside, but I often found myself learning almost as much from you as I learned from our instructors!  Your sense of humor, your persistence, your encouragement, and your willingness to share relevant articles, codes, methods - whatever you found! - with everyone else made this wonderful learning experience just that much better!  

Finally, I would like to offer my thanks to my friends and family.  Thank you for your encouragement, support, advice, and occasional snacks during this six-month-plus marathon of extreme virtual-learning!  Thank you for your willingness to help me practice my presentation with you, and thank you for your honest feedback for what needs to be fixed.
	- A special THANK YOU goes out to my friends **Tom Ward** and **Veronica Ikeshoji-Orlati**.  It was your advice and encouragement that led me to start this journey with NSS in the first place.  Thank you for helping me to think through complicated problems, for looking over bits of confusing code, and for helping me to research for solutions.  Thank you for letting me BORROW YOUR COMPUTER over an entire weekend (!) to run some problematic lines of code that were taking forever, and for then helping me to find a far more efficient way to solve that problem!  Thank you for seriously, and literally, everything!
	- A special thank you also goes out to my friend **Randy Moody**.  You helped me find a computer that allowed me to take this class, on short notice, well under my budget.  I don't know how you pulled that off, but I literally could not have done any of this without your providence!  

*Back to [Contents](#Contents)* 