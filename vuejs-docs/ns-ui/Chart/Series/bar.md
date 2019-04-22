---
title: Bar
page_title: Bar series | Progress NativeScript UI Documentation
description: This article gives a basic introduction of Bar series and continues with a sample scenario of how Bar series are used.
slug: chart-series-bar-vue
tags: series, cartesian, bar, vue, nativescript, professional, ui
position: 2
publish: true
---

# RadChart Bar Series
Bar Series are categorical type of series that represent the objects from the data source as bars with different length. To use Bar series, you need to initialize a {% typedoc_link classes:RadCartesianChart %}, define a {% typedoc_link classes:CategoricalAxis %} and {% typedoc_link classes:LinearAxis %} and bind the series to a set of data objects.

## Adjusting Bar Size
By default, the size of a bar is calculated based on the axis plot mode and the count of the categories from the data source. There are cases in which the automatically calculated size does not meet the specific application scenarios. By using the {% typedoc_link classes:BarSeries,member:minBarSize %} and {% typedoc_link classes:BarSeries,member:maxBarSize %} properties you can adjust the size of a single bar within the series. The properties accept values in device independent pixels. These properties define boundaries for the size of a bar.

### Example
Just like with all vue 'pages' let's start with the `Component` in which we will place our {% typedoc_link classes:RadCartesianChart %} instance.

Before that, we would create a basic JS or TS module that contains a collection of objects, which will be used by the chart to provide intuitive data visualization.

<snippet id='chart-get-countries-data-vue'/>

All that is left is to declare the template of the vue component in which we:

- Declare a {% typedoc_link classes:RadCartesianChart %}
- Declare the {% typedoc_link classes:CategoricalAxis %} and {% typedoc_link classes:LinearAxis %} between the {% typedoc_link classes:RadCartesianChart %} open and close tags
- After that set the **`tkCartesianHorizontalAxis`** and **`tkCartesianVerticalAxis`** directive to the axes
- Finally declare a {% typedoc_link classes:BarSeries %} instance to it, bind the {% typedoc_link classes:BarSeries,member:items%} to the source of data and set the **`tkCartesianSeries`** directive

<snippet id='chart-bar-series-vue'/>

> Depending on the required Bar orientation, you can swap the axes' position and assign the {% typedoc_link classes:CategoricalAxis %} to the {% typedoc_link classes:RadCartesianChart,member:horizontalAxis%} property and the Linear to the {% typedoc_link classes:RadCartesianChart,member:verticalAxis%} property. This will change the orientation of the bars to vertical.

![Cartesian chart: Bar series](../../../../ui/img/ns_ui/bar_series_android.png "Bar series on Android.") ![Cartesian chart: Bar series](../../../../ui/img/ns_ui/bar_series_ios.png "Bar series on iOS.")
