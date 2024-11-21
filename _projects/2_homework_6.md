---
name: Homework 6 
tools: [Python, HTML, vega-lite, Altair]
image: assets/pngs/cars.png
description: This is the Jekyll webpage that uses vega-lite and Altair for displaying interactive vizualizations for Homework 6!
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Homework 6: Jekyll Webpage


## Visualization 1 

The first visualization is a bar chart that displays the number of Bigfoot sightings across various U.S. states, categorized by seasons (Spring, Summer, Fall, Winter). This visualization aims to provide an understanding of how Bigfoot sightings are distributed geographically and seasonally, enabling viewers to identify states with high activity and any seasonal trends.

<vegachart schema-url="{{ site.baseurl }}/assets/json/bigfoot_bar_chart_viz1.json" style="width: 100%"></vegachart>

##### Design Choices:

This bar chart uses a combination of thoughtful encoding types and a carefully chosen color scheme to effectively communicate the distribution of Bigfoot sightings by state and season. The number of sightings is represented on the x-axis as a quantitative measure, allowing for an easy comparison of sightings across states. The y-axis represents the states as a nominal variable, sorted based on the increasing number of total sightings. Each bar is further segmented by season, with the seasons encoded using distinct colors from the reversed Inferno color scheme. This scheme provides high contrast and ensures the visualization is visually engaging and accessible. The darker shades in the color palette represent winter, while the lighter and brighter shades represent seasons such as fall and summer, effectively aligning the visuals with the expected seasonal variability. Additionally, the chart includes interactive tooltips that provide detailed information about the state, season, and exact number of sightings when a user hovers over a bar. The height of the visualization has been fixed, while the width is dynamic, allowing it to adjust based on the size of the webpage, ensuring optimal readability and usability.


The data underwent several transformations to ensure it was suitable for this visualization. Missing values in numerical columns were replaced with the median to preserve meaningful trends and prevent skewing caused by outliers. For categorical columns, missing values were replaced with the label "None" to ensure all states and seasons were represented, even in cases where data was incomplete. The dataset was then aggregated using the .groupby() function to calculate the total number of sightings for each state-season pair, enabling a deeper understanding of seasonal patterns within states. These transformations ensured the data was clean, comprehensive, and ready for visualization, ultimately enhancing the clarity and accuracy of the final chart.





## Visualization 2 

This visualization is a line chart that depicts the number of Bigfoot sightings over time, broken down by season. Each line represents a season (Winter, Spring, Summer, Fall), and the x-axis corresponds to the year of the sightings. The y-axis shows the total number of sightings in each year. The slider below the chart allows users to select a start and end year, dynamically filtering the data displayed in the chart.


<vegachart schema-url="{{ site.baseurl }}/assets/json/slider_line_chart.json" style="width: 100%"></vegachart>


##### Design Choices:

The x-axis uses an ordinal encoding for years to emphasize the temporal progression of sightings. The y-axis uses a quantitative encoding to display the number of sightings. Color encoding is applied to the season variable, using a distinct color for each season to allow clear differentiation between trends. This helps users quickly identify how sightings vary by season over time. A qualitative color scheme (Altair’s default) is used for the season variable. This ensures each season has a visually distinct color, making it easy to compare their respective trends. The dataset was grouped by year and season to calculate the total number of sightings for each combination. This was done using a groupby operation in Python.


##### Interactivity

A slider was added to filter the dataset dynamically based on user-selected start and end years. This filtering is applied through Altair's transform_filter operation.The slider adds interactivity, allowing users to explore specific ranges of years dynamically. This makes the visualization more engaging and helps users focus on specific periods of interest. For example, users can observe trends during a particular decade or compare seasonal trends over selected years, providing flexibility and deeper insight into the data.



<!-- CODE FOR SHOWING THE VISUALIZATION --> 
<!-- BELOW LINE READS THE JSON FILE THAT CONTAINS THE VEGA-LITE/ALTAIR CODE-->
<!-- <vegachart schema-url="{{ site.baseurl }}/assets/json/cars.json" style="width: 100%"></vegachart> -->













<!-- CODE FOR HYPERLINKING THE ANALYSIS AND THE DATA TO THE BUTTONS --> 
<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/Sharanya-20/Sharanya-20.github.io/blob/main/python_notebooks/Workbook.ipynb" text="The Analysis" %}
</div>

