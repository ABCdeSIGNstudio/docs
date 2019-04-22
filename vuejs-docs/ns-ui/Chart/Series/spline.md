---
title: Spline
page_title: Spline series | Progress NativeScript UI Documentation
description: This article gives a basic introduction of Spline series and continues with a sample scenario of how Spline series are used.
slug: chart-series-spline-vue
tags: series, cartesian, spline, vue
position: 5
publish: true
---

# RadChart Spline Series
{% typedoc_link classes:SplineSeries %} are categorical type of series that visualize the data objects as a series of dots connected with a spline, i.e. a curved line segments. To use Spline series, you need to initialize a {% typedoc_link classes:RadCartesianChart %}, define a {% typedoc_link classes:CategoricalAxis %} and {% typedoc_link classes:LinearAxis %} and bind the series to a set of data objects.

## Example
Just like with all vue 'pages' let's start with the `Component` in which we will place our {% typedoc_link classes:RadCartesianChart %} instance.

Before that, we would create a basic JS or TS module that contains a collection of objects, which will be used by the chart to provide intuitive data visualization.

<snippet id='chart-get-countries-data-vue'/>

All that is left is to declare the template of the vue component in which we:

- Declare a {% typedoc_link classes:RadCartesianChart %}
- Declare the {% typedoc_link classes:CategoricalAxis %} and {% typedoc_link classes:LinearAxis %} between the {% typedoc_link classes:RadCartesianChart %} open and close tags
- After that set the **`tkCartesianHorizontalAxis`** and **`tkCartesianVerticalAxis`** directive to the axes
- Finally declare a {% typedoc_link classes:SplineSeries %} instance to it, bind the {% typedoc_link classes:SplineSeries,member:items%} to the source of data and set the **`tkCartesianSeries`** directive

<snippet id='chart-spline-series-vue'/>

![Cartesian chart: Spline series](../../../../ui/img/ns_ui/spline_series_android.png "Spline series on Android.") ![Cartesian chart: Spline series](../../../../ui/img/ns_ui/spline_series_ios.png "Spline series on iOS.")
