# Boston_Food_Inspections
Analysis of Food Establishment Inspection data for Boston MA USA

Introduction:  This project uses python to analyze food establishment inspection data that is freely available online from the city of Boston. Establishments are inspected at least yearly to ensure compliance with  standards and requirements for food safety and graded with a letter scale.  If enough violations are found that would grade the establishment less than an A, the establishment is inspected again after 30 days and graded on that inspection.  The establishment can then elect to reinspect again if it doesn't like the score.  The latest score is posted by each restaurant.  Restaurants with a grade of A are inspected each year, B every six months, and C every three months. The problem with this though is that the letter grade is not really reflective of conditions at the establishment but that of the latest inspection after violations were found and corrected.  This project highlights violation data from the recent past (past year) that are not part of the grade so that restaurants can be compared to each other and concerned restaurant goers can make more informed choices about where they eat to minimize their chances of getting food poisoning.

Data: The data used for this project is available from https://data.boston.gov/dataset/food-establishment-inspections.  Some of the operations performed on the data to clean it are:
  
1) Violations from more than 365 days in the past were eliminated from the data such that old violations are not displayed.  The conditions at food establishments are always changing and annual inspections allow for a recent snapshot of restaurant cleanliness.
2) Establishments with missing lat/long data are sent to geopy to fill in missing data to later plot with folium.
3) Restaurants with where lat long cannot be obtained with the address given or there is incorrect address formatting are dropped from the set.
4) Violations for each restaurant are tabulated and a score is given for each location.  Each violation is only taken at 50% of what the actual estimated score penalty so all violations are weighed less.  The score ranges from a 100 to a 0.  Greater than 90 is green, 75, yellow, 60 orange, and 50 red.
5) The restaurants will then be run through foursquare servers to obtain the number of likes for each establishment.  
6) Each restaurant is then plotted on a folium map such that the marker color allows for comparison of violations between restaurants, and the marker size represents the popularity of the location in terms of the likes it receives through social media.
7) Violations from the past year are all visible when each marker is clicked if users want to see why the establishment is scored the way it is.


