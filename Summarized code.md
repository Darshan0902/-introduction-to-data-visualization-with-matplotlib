# Introduction to Data Visualization with Matplotlib.

## Chapter-1 : Introduction.

_This chapter introduces the Matplotlib visualization library and demonstrates how to use it with data._

<h3> Importing essential Libraries.<h3>
  
```

# Importing the course packages
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Importing the course datasets 
climate_change = pd.read_csv('datasets/climate_change.csv', parse_dates=["date"], index_col="date")
medals = pd.read_csv('datasets/medals_by_country_2016.csv', index_col=0)
summer_2016 = pd.read_csv('datasets/summer2016.csv')
austin_weather = pd.read_csv("datasets/austin_weather.csv", index_col="DATE")
weather = pd.read_csv("datasets/seattle_weather.csv", index_col="DATE")

# Some pre-processing on the weather datasets, including adding a month column
seattle_weather = weather[weather["STATION"] == "USW00094290"] 
month = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"] 
seattle_weather["MONTH"] = month 
austin_weather["MONTH"] = month
  
```
  
  <h4> (i) Using the matplotlib.pyplot interface </h4>
  
  _INSTRUCTIONS_
<br> 1. Import the matplotlib.pyplot API, using the conventional name plt.<br>
<br> 2. Create Figure and Axes objects using the plt.subplots function.<br>
<br> 3. Show the results, an empty set of axes, using the plt.show function.<br>
  
 ```
  # Import the matplotlib.pyplot submodule and name it plt
import matplotlib.pyplot as plt

# Create a Figure and an Axes with plt.subplots
fig, ax = plt.subplots()


# Call the show function to show the result
plt.show()
  ```
  
  OUTPUT : 
  ![image](https://user-images.githubusercontent.com/77969007/234915057-aad4925e-5f06-427d-8d67-7dba6bb29a87.png)

  <h4> (ii.) Adding data to an Axes object </h4>
  
  _INSTRUCTIONS_:
  
1.Import the matplotlib.pyplot submodule as plt.<br>
2.Create a Figure and an Axes object by calling plt.subplots.<br>
3.Add data from the seattle_weather DataFrame by calling the Axes plot method.<br>
4.Add data from the austin_weather DataFrame in a similar manner and call plt.show to show the results.<br>
  
  ```
  
  # Import the matplotlib.pyplot submodule and name it plt
import matplotlib.pyplot as plt

# Create a Figure and an Axes with plt.subplots
fig, ax = plt.subplots()

# Plot MLY-PRCP-NORMAL from seattle_weather against MONTH
ax.plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"])

# Plot MLY-PRCP-NORMAL from austin_weather against MONTH
ax.plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"])

# Call the show function
plt.show()
  
  ```
  
  _output:_
  
  ![image](https://user-images.githubusercontent.com/77969007/234919682-254238aa-be99-44ce-a50e-b225e25453ed.png)

  <h4> (iii.) Customizing data appearance </h4>
  
 <br>Call ax.plot to plot "MLY-PRCP-NORMAL" against "MONTHS" in both DataFrames.<br>
<br>Pass the color key-word arguments to these commands to set the color of the Seattle data to blue ('b') and the Austin data to red ('r').<br>
<br>Pass the marker key-word arguments to these commands to set the Seattle data to circle markers ('o') and the Austin markers to triangles pointing downwards ('v').<br>
  
  ```
  # Plot Seattle data, setting data appearance
ax.plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"],
        color='b', marker='o', linestyle='--')

# Plot Austin data, setting data appearance
ax.plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"],
        color='r', marker='v', linestyle='--')

# Call show to display the resulting plot
plt.show()
  ```
  
  _OUTPUT:_
  
  ![image](https://user-images.githubusercontent.com/77969007/234920212-493821c0-6b98-46db-9543-3254d782d36f.png)
  
  <h4> (iv.) Customizing axis labels and adding titles </h4>
  
  _INSTRUCTIONS:_
  
  <br>Use the set_xlabel method to add the label: "Time (months)".
<br>
  <br>Use the set_ylabel method to add the label: "Precipitation (inches)".
<br>
  <br>Use the set_title method to add the title: "Weather patterns in Austin and Seattle".
<br>
  
  ```
  
  ax.plot(seattle_weather["MONTH"], seattle_weather["MLY-PRCP-NORMAL"])
ax.plot(austin_weather["MONTH"], austin_weather["MLY-PRCP-NORMAL"])

# Customize the x-axis label
ax.set_xlabel("Time (months)")

# Customize the y-axis label
ax.set_ylabel("Precipitation (inches)")

# Add the title
ax.set_title("Weather patterns in Austin and Seattle")

# Display the figure
plt.show()
  
  ```
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

  
  
