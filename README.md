# DSA 202: Data Visualization

North Carolina State University, Spring 2026

This repository contains coursework completed for DSA 202, a course covering data visualization principles, accessibility-first chart design, and dashboard construction across Excel, R, and Tableau. The work progresses across four deliverables and culminates in a published interactive dashboard, titled Olympic Success Around the World.

## Project: Olympic Success Around the World

**Core question:** Do richer countries always win more Olympic medals, and how does the relative scale of the Summer versus Winter Games affect that picture?

**Datasets:**

| Dataset | Source | Coverage |
|---|---|---|
| Olympic Games athlete events and results | Kaggle | 1896 to 2016 |
| GDP per capita | Our World in Data, World Bank | 1990 to 2020 |

**Key finding:** Olympic success is concentrated among a small number of wealthy, densely populated countries with established sports infrastructure, most prominently the United States. GDP per capita is a partial predictor at best. Norway, Luxembourg, and Qatar have high GDP but relatively few medals, while Russia and China have many medals despite lower GDP per capita.

**Live dashboard:** [Tableau Public](https://public.tableau.com/app/profile/khushi.chaturvedi5804/viz/OlympicSuccessAroundtheWorld/Dashboard1)

## Project Progression

### Assignment 1, Accessible Chart Design in Excel

Built an accessibility focused bar chart using astronaut mission data, applying core accessibility principles that carried through the rest of the project:

- A takeaway style title that states the finding, not just the topic
- Direct data labeling, rather than requiring axis estimation
- Deliberate color and contrast choices, avoiding reliance on color alone to convey meaning
- Intentional use of white space to reduce visual clutter
- Screen reader alt text

### Assignment 2, Grammar of Graphics in R

Built the "Olympic medal records over time by season" line chart in R, using `ggplot2` and `dplyr`. The chart aggregates medal counts by year and season, and distinguishes Summer from Winter Games using color, line type, and point shape simultaneously, so the distinction remains readable for viewers with color vision differences.

Key code pattern:

```r
scale_color_manual(values = c("Summer" = "#E8851A", "Winter" = "#1A6FB8")) +
theme_minimal()
```

### Assignment 3, Interactive Dashboard in Tableau

Built the initial two chart Tableau dashboard: a stacked bar chart of medal count by nation, and a choropleth world map of worldwide medal distribution. The two datasets were merged and linked by country identifier, and this assignment established the visual language, including color encoding and geographic country roles, used in the final version.

### Final Deliverable, Full Four Chart Data Story

Expanded the dashboard to four coordinated visualizations, published to Tableau Public, and packaged with a full written narrative and a formal poster.

## The Four Visualizations

1. **Medal Count by Country, stacked bar chart.** Top performing nations broken down by gold, silver, and bronze medals. The United States is a clear outlier at more than 5,000 total medals.
2. **GDP per Capita versus Medal Count, scatter plot.** Plots each country's average GDP per capita against its total medal count, showing a general positive relationship that breaks down for several notable outliers in both directions.
3. **Medal Map, choropleth.** World map shaded by total medal count using Tableau's built in geographic country roles, showing medal concentration in North America, Europe, Russia, East Asia, and Oceania.
4. **Olympic Medal Records Over Time by Season, line chart.** Built in R with `ggplot2`, showing Summer Games medal totals consistently outpacing Winter totals across history, reflecting the larger number of Summer events and broader global participation.

## Design and Accessibility Principles Applied

- Redundant encoding, using color together with shape or line type, so charts do not rely on color perception alone
- Takeaway oriented titles that state the finding rather than only naming the topic
- Direct data labeling to avoid forcing axis estimation
- Deliberate contrast and reduced visual clutter, including removal of redundant legends and gridlines
- Alt text included for screen reader accessibility

## Tools and Libraries

Microsoft Excel (PivotCharts and built in accessibility features), R with `ggplot2` and `dplyr`, and Tableau (dashboard design, geographic mapping, dataset blending, and Tableau Public publishing).

## Reproducing the Analysis

1. **Assignment 1:** Open `DSA_202_-_Assignment_1.xlsx` in Excel. All chart formatting and data are self contained in the workbook.
2. **Assignment 2:** Open `DSA202_603_SP26_A2_kchatur.Rmd` in RStudio, install `tidyverse`, and knit the document to reproduce the line chart.
3. **Assignment 3 and Final Dashboard:** Open `DSA202_SP26_A3_kchatur.twbx` in Tableau Desktop or Tableau Public to explore the packaged workbook and underlying data sources directly. The final, published version of the dashboard is also available live at the Tableau Public link above.
