# Business Understanding

My company is expanding in to new industries to diversify its portfolio. Specifically, we are interested in purchasing and operating airplanes for commercial and private enterprises, but do not know anything about the potential risks of aircraft. I am charged with determining which aircraft are the lowest risk for the company to start this new business endeavor. I must then translate your findings into actionable insights that the head of the new aviation division can use to help decide which aircraft to purchase.

# Data

In the data folder is a [dataset](https://www.kaggle.com/datasets/khsamaha/aviation-accident-database-synopses) from the National Transportation Safety Board that includes aviation accident data from 1962 to 2023 about civil aviation accidents and selected incidents in the United States and international waters.

# Data Understanding

After exploring the schema:

    1. There are 31 columns, 5 columns of data type float 64 and the rest are string. There are 88889 rows of data
    2. There are only 4 columns with no null values, There are 13 columns with over 10000 null values
    3. There are duplicate values in the following columns:

            a. Make
            b. Injury.Severity
            c. Engine Type
            d. Purpose of flight
            e. Weather Condition
            f. Purpose of flight

    4. The date column is currently in the string format, this needs to be changed

## Data Preparation

Here is a brief summary of this section:

1. I am removing 7 columns with over 30000 null values in each column as this is over 30% of the data points. Some columns had well over 50% null values. These columns did not add to understanding the safety of the airplanes either so, i removed them. Therefore this does not reduce quality of dataset 
2. I am removing rows with null values. Any column that has 1000 rows or less with null values I removed those rows. Overall this came to ~1500 rows, so this did not reduce quality of data 
3. In the Make column, makes are repeated because of the same name written in different cases and with additional information. I have fixed this by making all the cases uniform. I also applied a formula such that, for example, the make "Cessna", there were multiple instances where there would be a "Cessna ABC" and "Cessna XYZ". In such cases, I combined them into one make "Cessna" 
4. The weather conditions column had the same issue as in the make column and this was fixed in the same way as above.
5. Date column was converted from string to date format
6. Injury Severity column had an issue where "Fatal" was repeating over again. This was fixed in the same way as above.

# Exploratory Data Analysis

Through the process of data analysis I explored:

    a. The number of Fatalities by Purpose of travel, type of engine, weather conditions, phase of flight 
    b. The historical trend of number of fatalities injuries each year
    c. The Under/Over representation of Makes to the Total Fatalities

Based on the analysis above, I have reached conclusions and recommendations which have been mentioned below after the data analysis section

# Conclusion

1. More Fatal Accidents have happened during personal travel than any other purpose of travel

![img](.data/images/Fatbypurpose.png)


2. Weather plays a more important factor than the type of plane. Under poorer weather conditions with less visual clarity, nearly 80% of accidents are fatal accidents, whereas under better visual conditions, only ~20% of incidents are fatal

Nearly 80% of accidents under VMC conditions are Non-Fatal as seen below.

![img](.data/images/FatbyVMC.png)

Nearly 60% of accidents under IMC conditions are Fatal as seen below

![img](.data/images/FatbyIMC.png)

Clearly weather plays a strong role in the cause of accidents


3. Although Fatal accidents have been occuring until very recently. Not many have happened recently in Executive or Corporate/Jet travel

![img](.data/images/FatbyYearexec.png)


4. Planes with Reciprocating engines are the ones with the highest number of fatalities, so it is best to avoid such planes. Turbojets have the lowest number of fatalities

![img](./data/images/FatbyEngine.png)


5. According to the entire dataset, the most fatalities occured during the "Cruise" Phase of flight, however, the highest fatalities in executive/corporate travel occured during the "Approach" phase of the flight. Pilots flying corporate jets have to be particularly more careful when approaching

![img](.data/images/Fatbyphase.png)


## Limitations

1. We are considering plane options from a perspective of safety. There are other factors to consider:
    
        a. Cost - What budget does the company have. Will the company have access to financing to purchase the plane
    
        b. Passenger Capacity: How many people would like to travel at a time?
    
        c. Flight Range: What kind of distances would the company look at traveling
    
    
 2. Even when looking at safety there are other factors to consider:
     
         a. Most fatal accidents have happened under poorer visual conditions. Perhaps rather than focusing on the type of             plane, it might be better to focus on the flying conditions and fly during better weather conditions
     
 
 3. When assessing safety from the point of view of Total Fatal Injuries, it can be misleading as we don't know the plane passenger capacity. For example, we see that Cessna planes have the highest proportion of fatal injuries. That could be a safety issue, or it could be they are bigger planes carrying more people so, when there is an accident it is likely to have more fatal injuries

## Recommendations

1. Avoid flying if inclement weather is forecasted. Weather plays a very strong role in creating accidents as the data has shown above. Therefore, it is very important that pilots pay attention to weather forecasts when preparing to travel. Executives must take calls to avoid travel if inclement weather is forecasted as the type of plane becomes irrelevant in that case.

2. Avoid reciprocating engine as aircrafts with these engines are involved in the highest number of fatalities. Aircrafts with Turbojet engines have the lowest fatalities so I would recommend an aircraft with a Turbojet

3. Develop Approach through the use of flight simulators. The highest number of fatalities have occured during the Approach phase of the flight. So it is very important that pilots take care and develop their approach skills through the use of flight simulators. 

4. Final recommendation of aircraft:Since our intended purpose of travel is Corporate travel, Learjets are underrepresented in terms of total fatal accidents. Meaning Learjets make up 3% of the total incident/accident but only represent 1% of the total fatalities. So among the Learjet I would recommend one with a Turbojet engine as those are the ones with the least number of incidents and fatalities, so to name one model it would be a Learjet LR -25. There are other Makes of planes with lower number of fatalities than Learjet but those numbers are too small to have any statistical significance.


## Next Steps

We have researched planes from a safety perspective. Next we would need to look at the data from other angles as mentioned in the limitation section e.g. budget, passenger capacity flight range etc.

## For More Information

See the full analysis in the [Jupyter Notebook](./notebook.ipynb) or review this [presentation](./presentation_phase_1.pdf).

To access the Tableau dashboard please use this [link](https://public.tableau.com/app/profile/balram.ottapathu/viz/AircraftDashboard_16889579776570/Dashboard1#1)

For additional info, contact Balram Ottapathu at [balramo92@gmail.com](mailto:balramo92@gmail.com)



## Repository Structure

```
├── data
├── images
├── notebook.ipynb
├── README.md
├── presentation_phase_1
``` 




