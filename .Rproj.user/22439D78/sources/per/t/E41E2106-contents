# Energy Use Forecast - IOT Predictive Modeling

# Pacotes

library(ggplot2)
library(dplyr)
library(randomForest)

# Load the dataset
data <- read.csv("projeto8-training.csv")

# Explore the data
summary(data)
View(data)

names(data)
#date: The date and time of the sensor reading.
#Appliances: The amount of power being used by appliances in the home.
#lights: The amount of power being used by lights in the home.
#T1: The temperature reading from sensor 1.
#RH_1: The relative humidity reading from sensor 1.
#T2: The temperature reading from sensor 2.
#RH_2: The relative humidity reading from sensor 2.
#etc.: The rest of the columns are temperature and relative humidity readings from other sensors in the home.
#T_out: The outdoor temperature.
#Press_mm_hg: The outdoor pressure.
#RH_out: The outdoor relative humidity.
#Windspeed: The wind speed.
#Visibility: The visibility.
#Tdewpoint: The dew point.
#rv1: The rain volume reading from sensor 1.
#rv2: The rain volume reading from sensor 2.
#NSM: The number of significant moistures.
#WeekStatus: The day of the week.
#Day_of_week: The name of the day of the week.

#Considering this supposition of the dataset, i understand that the Energy use is defined by Appliances + lights.
# Create a new dataset with total power
new_data <- data %>%
  mutate(total_power = Appliances + lights) %>%
  select(-Appliances, -lights)

# Print the new dataset
View(new_data)

# Create a RandomForest model
model <- randomForest(total_power ~ ., data = new_data, ntree = 500)

# Get the importance of the features
importance <- importance(model)

# Print the top 10 features
#print(importance[1:10, ])
print(importance)
