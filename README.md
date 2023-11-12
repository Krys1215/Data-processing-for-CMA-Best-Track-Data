# Description   
The current version of the CMA Tropical Cyclone Optimal Path dataset provides the position and intensity of tropical cyclones in the waters of the Northwest Pacific Ocean (including the South China Sea, north of the equator and west of 180°E) for each 6-hour period since 1949, which are placed in separate text files according to the year, and will be added year by year in the future.   
   
Starting from 2017, for typhoons making landfall in China, the frequency of the best track time is encoded to once every 3 hours during the 24-hour period before their landfall.   
   
Starting from 2018, for typhoons making landfall in China, the frequency of the best track time is encoded to once every three hours during the 24-hour period before landfall and during the period of land activities in China.   
   
# File Format   
CHYYYYBST.txt --   
   
CH: taken from English CHINA, indicating that this dataset is compiled by China;    
   
YYYY: is the year, expressed as four digits;   
   
BST: taken from English BEST TRACK, indicating that this dataset is the best path dataset.   
   
# Document content format   
## 1. Header Lines   
![Header](https://tcdata.typhoon.org.cn/images/best-track-data-format-pic_1.png)   
| Field | Length | Description |
|-------|--------|-------------|
| AAAAA | 5      | Classification flag; '66666' indicates the best track data. |
| BBBB  | 4      | International number; the last two digits of the year + two-digit serial number. |
| CCC   | 3      | Number of rows in the track data record. |
| DDDD  | 4      | Serial number of tropical cyclones, including tropical depressions. |
| EEEE  | 4      | China's identification number for tropical cyclones. |
| F     | 1      | Tropical cyclone termination record: 0 for dissipation, 1 for moving out of the responsibility area of the Western Pacific Typhoon Committee, 2 for merging, 3 for quasi-stationary. |
| G     | 1      | Hourly interval between each row of the path; before 2017, it was 6 hours, starting from 2017, individual cases with a 3-hour encryption record are marked as 3, and others remain 6. |
| H...H | 20     | English name of the tropical cyclone; "(-1)n" is added after the name to indicate the secondary center and its serial number. |
| I...I | 8      | Date on which the dataset is formed. |
   
## 2. Data Lines   
![Data Lines](https://tcdata.typhoon.org.cn/images/best-track-data-format-pic_2.png)   
| Field          | Description |
|----------------|-------------|
| YYYYMMDDHH     | Date and time in UTC: YYYY year, MM month, DD day, HH hour. |
| I              | Intensity marker based on the average wind speed within 2 minutes around the exact time point. Refer to the National Standard "Tropical Cyclone Grades" (GB/T 19201-2006): <br> 0 - Weaker than Tropical Depression (TD), or intensity unknown. <br> 1 - Tropical Depression (TD, 10.8-17.1 m/s). <br> 2 - Tropical Storm (TS, 17.2-24.4 m/s). <br> 3 - Severe Tropical Storm (STS, 24.5-32.6 m/s). <br> 4 - Typhoon (TY, 32.7-41.4 m/s). <br> 5 - Severe Typhoon (STY, 41.5-50.9 m/s). <br> 6 - Super Typhoon (SuperTY, ≥51.0 m/s). <br> 9 - Extratropical transition, the first digit indicates the completion of the transition. |
| LAT            | Latitude (0.1°N). |
| LONG           | Longitude (0.1°E). |
| PRES           | Central minimum pressure (hPa). |
| WND            | 2-minute average maximum sustained wind speed near the center (MSW, m/s). WND=9 indicates MSW < 10 m/s, WND=0 indicates missing data. |
| OWD            | 2-minute average wind speed (m/s) with two cases: <br> (a) For tropical cyclones making landfall in China, it represents the wind speed of coastal strong winds. <br> (b) When a tropical cyclone is in the South China Sea, it represents the maximum wind speed within a range of 300-500 km from the center. |   

# Citation   
Ying, M., W. Zhang, H. Yu, X. Lu, J. Feng, Y. Fan, Y. Zhu, and D. Chen, 2014: An overview of the China Meteorological Administration tropical cyclone database. J. Atmos. Oceanic Technol., 31, 287-301. doi: 10.1175/JTECH-D-12-00119.1
Lu, X. Q., H. Yu, M. Ying, B. K. Zhao, S. Zhang, L. M. Lin, L. N. Bai, and R. J. Wan, 2021: Western North Pacific tropical cyclone database created by the China Meteorological Administration. Adv. Atmos. Sci., 38(4), 690−699. doi: 10.1007/s00376-020-0211-7   
