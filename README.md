### Coupon Acceptance Analysis

The objective of this activity is to determine the acceptance of coupon by drivers using various features presented in the dataset.

## The following are the transformations done on the variables
* Feature "Car" was dropped due to 99 % of its values being missing.
* There are few other features missing less than 2 % of its value. For those missing values, mode of those feature values were calculated and populated. 
* Feature "toCoupon_GEQ5min" contained only one value which was 1. Therefore the column was dropped
* Features "direction_same" and "direction_opp" are mutually exclusive. So the column "direction_opp" was dropped as its value can be infered from the other variable.

## Analysis of bar coupon
* Proportion of bar coupons were accepted is 41.0 %.
* No bar coupons were accepted by the drivers having <b>kids</b> as passanger
* Below is the visual of acceptance and rejection rate of bar coupons based on the categorical features of the dataset.
![image](https://github.com/vizjay/Coupon-Acceptance-Analysis/assets/122194901/cf3083e5-4cdb-4395-a5e0-2cd68cc4c3ff)

* Proportion of bar coupons accepted by driver's destination and if the coupon venue is in the same direction as that of destination.
  - Drivers not travelling to any <b>urgent place</b> has the highest acceptance rate at <b> 20.72 %</b> when the venue is in the opposite direction as that of destination.
  - Drivers travelling <b>home</b> has a <b>8.28 %</b> acceptance rate when the venue is in the same direction. If the venue is in the opposite direction, then the acceptance rate drops to <b>3.17 %</b>
  - Drivers travelling to <b>Work</b> has a <b>1.29 %</b> acceptance rate when the venue is in the same direction. If the venue is in the opposite direction, then the acceptance increases to <b>7.54 %</b>
  
* Analysis based on the frequency of drivers going to bar:
  - Acceptance rate of drivers going to bar <b>less than 3 times</b> a month has the highest rate at <b>33.42 %</b> than the drivers who went to bar <b>more than 3 times</b> a month having the acceptance rate of <b>7.59 %</b>.
* Below is the visual of the acceptance rate of bar coupons by occupation
  
  ![image](https://github.com/vizjay/Coupon-Acceptance-Analysis/assets/122194901/38595429-39c2-4c91-b265-bf2487e2d7a3)

* <b>Student</b> and <b>Unemployed</b> have the highest acceptance rate for coupon at <b>6% and 5%</b> respectively.
* Proportion of bar coupons accepted by driver's who are currently employed. We need to remove the occupations <b>Student</b>, <b>Unemployed</b> and <b>Retired</b> as these belong to not working category.
  - Drivers who are <b>working</b> and over 25 years old had a much higher <b>(24 %)</b> acceptance rate than drivers who are <b>working</b> and under 25 years old <b>(5%)</b>.

## Analysis of Restaurant(20-50) coupon
* Proportion of expensive restaurant coupons (Restaurant(20-50)) accepted is 44.1 %
* Below is the visual of acceptance and rejection rates of restaurant coupons based on the categorical features of the dataset.

  ![image](https://github.com/vizjay/Coupon-Acceptance-Analysis/assets/122194901/08ba3f00-1993-41fe-9ba4-5149d8b53b7e)

* Proportion of coupons accepted by driver's who went to restaurant 3 or fewer times a month to those who went more.
  - Drivers who went to restaurant <b>more than 3 times a month</b> accepted <b>fewer</b> coupons (5.3 %) than drivers who went <b>less than 3 times</b> (39 %). Also,
    Drivers with age <b>over</b> the median age of <b>31 years </b> accepted <b>less</b> coupons than drivers <b>under 31</b>.
    
 ##### Since drivers who went to resturant less than 3 times accepted more coupons, lets include other features to this data to see how the acceptance rate is affected.
 * Check the income distribution of drivers who goes to restaurant less than 3 times a month and accepting coupon
   - There is no big difference in acceptance rate between low and high earning drivers; 50.95 % vs 49 %.
     
 * Compare the acceptance rate of drivers going to restaurant less than 3 times a month against their working status. We will consider students and unemployed as not working and other occupations as working.
   - Drivers who went to restaurant <b>less than 3 times</b> and are <b>employed</b> accepted more coupons (29%) than drivers who are either unemployed or a student (9%).
     
 *  Compare the acceptance rate of drivers going to restaurant less than 3 times a month against the proximity of their destination to the restaurant venue. Here, value 1 indicates time to venue is within the given minute and 0 indicates time to venue is not within the given minute.
    - For distance to venue less than or equal to 15 mins, drivers going in the opposite direction going in opposite direction accepted more coupons <b>(20%)</b> than drivers travelling in same direction <b>(1%)</b>. This is because all drivers going <b>home</b> as their destination aren't accepting many coupons.
