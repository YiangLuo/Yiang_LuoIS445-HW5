# 🛸 UFO Sightings Interactive Dashboard

This webpage presents two interactive visualizations created with Altair to explore UFO sighting patterns in the United States. Each chart includes a description, design rationale, and explanation of data processing steps.

---

## 📈 Chart 1: UFO Sightings Over Time (Interactive Range Selection)

<iframe src="chart1.html" width="100%" height="500"></iframe>

**Chart Description:**  
This chart shows the yearly trend of UFO sightings between 1900 and 2020. The main chart is in the form of a line graph that clearly shows the increase or decrease in the number of sightings recorded in each year. Below the chart is an interactive light-colored area chart that allows users to drag the time range slider to view detailed trend changes over a selected time period in the main chart. This design helps users explore fluctuations in UFO sightings between specific years in a more flexible manner.

**Design Choice:**  
The use of a line chart in the main graph clearly conveys the trend of UFO sightings over the years. The area chart below the graph provides a time range selector as an “overview graph”, allowing users to interactively focus on the details of the data over time, with the year on the X-axis and the number of sightings on the Y-axis, with clear axes headings. The number of sightings per year is also displayed as a reminder text when the mouse is hovered over. The entire chart is set to 600 pixels in width, 400 pixels in height for the main chart, and 60 pixels for the overview chart, making it ideal for displaying beautifully on a web page.

**Data Conversion:**  
To generate the chart, the datetime field in the raw data was first converted to a standard date and time format. Next, the corresponding year field was extracted and forced to an integer for grouping purposes. The number of UFO sightings per year was then aggregated by year using the groupby and size() functions to form the final year_counts data frame for plotting. During this process, records with missing datetime data were also removed to ensure the completeness and accuracy of the time series.

---

## 📊 Chart 2: UFO Shape Distribution by State (Dropdown Filter)

<iframe src="chart2.html" width="100%" height="600"></iframe>

**Chart Description:**  
This is a user-selectable bar chart showing the distribution of UFO shapes in different U.S. states. Users can select any state from the drop-down menu on the left, and the chart will instantly update to show the number of sightings of each type of UFO shape in that state. The colors of the bars indicate the different UFO shapes, and the legend on the right hand side of the chart clearly shows how the colors correspond to the shapes. The chart allows users to quickly compare the distribution of common and uncommon UFO shapes in each state.

**Design Choice:**  
The bar chart distinguishes different UFO shapes by color and uses a legend to further help users identify them. The horizontal axis is the UFO shape (shape category), the vertical axis is the number of sightings, and the bars in the graph are arranged in descending order of the number of sightings, highlighting the most common shapes. A drop-down menu is added on the left side to allow the user to select a state name, and the chart automatically responds to the selection and filters the data to show only the corresponding state. In addition, a mouse hover displays a tooltip containing the shape name and number of sightings. The width of the chart is set to 600 pixels and the height to 400 pixels, making it suitable for web display.

**Data transformation:**  
During data processing, records with missing state or shape were first deleted to retain valid observations. Then groupby was used to aggregate the data by state and shape and count the number of sightings for each shape. Based on this, all unique state names were extracted, sorted, and used to bind Altair's dropdown selector. Interactive selection logic is built using selection_point, and dynamic data filtering based on user selection is implemented using transform_filter, enabling real-time interactive updating of the chart.
---

## 🔗 References

- 📂 [View the original UFO dataset](https://www.kaggle.com/datasets/NUFORC/ufo-sightings)  
- 🧠 [View this notebook on GitHub](https://github.com/YiangLuo/Yiang_LuoIS445-HW5)

