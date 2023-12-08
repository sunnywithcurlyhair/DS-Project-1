# DS-Project-1

## Overview
* Purpose: Management recommendations for purchasing and operating aircrafts based on safety
* Source of data: The NTSB aviation accident database - aircrafts accident data for the past 40 years 
* Focus areas and considerations:
  * Primary safety metric: the percentage of passengers with minor or no injury
  * Others : Weather conditions, Aircraft costs, Aircraft damages

## Data Analysis & Recommendations

* Based on the safety metric established, we broke down the data and filtered for the top 15 makes with the highest percentage of passengers with no/minor injury in the NTSB aviation accident database for further analysis - we saw that out of the top 15 makes, Boeing, Airbus, and Bombardier were the most closely distributed to the mean.
We then analyzed the distribution of the safety metrics of these 15 makes further, bifurcated by weather conditions, and found that Boeing, Bombardier and Saab Scania as the most ideal in enduring all kinds of conditions and made specific model recommendations from these makes where there are no fatalities or serious injuries.

<img width="1081" alt="Screenshot 2023-12-08 at 11 44 51 AM" src="https://github.com/WesleyDickens/DS-Project-1/assets/8894178/e3997252-dc83-4aca-9417-cd9874d983bf">

* Based on our pricing per seat analysis - the bombardier Crj1 is the most cost effective plane that passed our safety standards. The Boeing 720-025 was a close second and is our go to choice if the company wants higher capacity planes.

<img width="1051" alt="Screenshot 2023-12-08 at 11 44 26 AM" src="https://github.com/WesleyDickens/DS-Project-1/assets/8894178/69f3910a-895c-44a1-af72-3824a00c31d2">

* The Midwest region is the safest area to operate in from a human-life perspective and from a cost-savings perspective because it accounts for the lowest fatality rate in our set of recommended aircraft and has the lowest rate of destroyed aircraft when compared to other regions. 

<img width="1050" alt="Screenshot 2023-12-08 at 11 45 01 AM" src="https://github.com/WesleyDickens/DS-Project-1/assets/8894178/0c92b0fa-2ce1-4eb7-939b-d47890eb5769">
<i>This data is available to be further filtered and explored here: https://tinyurl.com/AviationAnalysis</i>

## Data we excluded
### Columns
* Air Carrier
* Publication Date
* Purpose of flight
* Latitude 
* Longitude
* Accident Number
* Event Id
* Airport Code 
* Airport Name 
* Registration Number 
* FAR Description

We excluded these columns because we don't believe they are relevant to our analysis and so they were dropped in order to maximize efficiency and usability of the dataset. 

### Rows
#### Amateur Built
All rows where Amateur.Built=True were dropped as those aircraft not built by professionals wouldn't be relevant to a company interested in operating aircraft at an enterprise scale. 
#### Total Passengers
Firstly we created a new dataframe column `total_passengers` that added together all the Injury columns and the Uninjured columns to get a flight manifest count. 

We dropped all rows where total_passengers==0 because those records are either errors or aren't relevant to our analysis. 
