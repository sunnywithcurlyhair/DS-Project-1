# DS-Project-1

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

#### Category & Make

We dropped all rows that either aren't in the 'Airplane' category or weren't made by a select number of high-profile aircraft manufacturers (list below). We excluded these because categories such as Balloons and Ultralight aircraft again wouldn't be relevant to a company interested in enterprise-level aircraft. 

* Aircraft companies -- 
`'Boeing', 'Airbus Industrie', 'Airbus', 'Bombardier' , 'Boeing Stearman' , 'Gulfstream Aerospace' , 'Boeing Helicopters Div.' , 'Gulfstream American' , 'Gulfstream-schweizer' , 'Bombardier Inc.' , 'Bombardier Aerospace Inc.' , 'Airbus Industries' , 'Gulfstream'`

