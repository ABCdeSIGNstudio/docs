---
title: Overview
page_title: Series overview | Progress NativeScript UI Documentation
description: An overeview of all series supported by Telerik Chart for NativeScript
slug: chart-series-overview-angular
tags: series, cartesian, pie, angular
position: 1
publish: true
---
# RadChart Series
Telerik Chart for NativeScript comes with a bunch of series suitable for different types of data. There are two main chart types: `Cartesian` and `Pie`. Each of these chart types requires corresponding series types to be able to visualize the data. For {% typedoc_link classes:RadCartesianChart %} you need to use {% typedoc_link classes:CartesianSeries %}, and for {% typedoc_link classes:RadPieChart %} you need to use {% typedoc_link classes:PieSeries %}. `CartesianSeries` are represented by two main series types: scatter and categorical.

All series expose the following properties:

- {% typedoc_link classes:ChartSeries,member:showLabels%} - determines whether labels are shown for each data point
- {% typedoc_link classes:ChartSeries,member:legendTitle%} - determines the title which will be displayed in the legend for the current series
- {% typedoc_link classes:ChartSeries,member:valueProperty%} - determines the name of the property on the source object that will provide the value used to plot the object in the chart
- {% typedoc_link classes:ChartSeries,member:items%} - used to bind the series with a source of data items
- {% typedoc_link classes:ChartSeries,member:selectionMode%} - responsible for the selection mode of the series.
The values are:
    - {% typedoc_link enums:ChartSeriesSelectionMode,member:None%} - the series cannot be selected
    - {% typedoc_link enums:ChartSeriesSelectionMode,member:NotSet%} - the series selection is not set, the selection mode set to chart will be used
    - {% typedoc_link enums:ChartSeriesSelectionMode,member:Series%} - the whole series will be selected
    - {% typedoc_link enums:ChartSeriesSelectionMode,member:DataPoint%} - the touched data point will be selected only
    - {% typedoc_link enums:ChartSeriesSelectionMode,member:DataPointMultiple%} - multiple touched data points will be selected
- {% typedoc_link classes:ChartSeries,member:labelStyle%} - property of type PointLabelsStyle defining the style of the point labels

## Categorical Series
The {% typedoc_link classes:CartesianSeries%} are used for visualizing data objects that can fit into a given category and expose a value assigned to that category. Examples for categorical series include:

- {% typedoc_link classes:BarSeries%}
- {% typedoc_link classes:LineSeries%}
- {% typedoc_link classes:AreaSeries%}
- {% typedoc_link classes:SplineSeries%}, etc.

As `CartesianSeries` all categorical series share the base cartesian series API and provide a couple of additional properties needed for their proper initialization. The following properties are part of this object and are needed for correctly setting up a categorical chart:

- {% typedoc_link classes:CartesianSeries,member:categoryProperty%} - defines the name of the property on the data object which will be used to plot the object into the right category
- {% typedoc_link classes:CategoricalSeries,member:stackMode%} - defines how separate series are combined within a single chart

#### Example

Here's a simple scenario using Bar series. In our NativeScript application we define the `Component` in which we will place our {% typedoc_link classes:RadCartesianChart %} instance. We create a basic angular `Component` that contains a collection of objects provided by an custom service, which will be used by the chart to provide intuitive data visualization.

The service is a simple 'mock' of an backend call that will return an array of objects:

<snippet id='chart-angular-data-service'/>

Inside that service we have a single function which returns an array:

<snippet id='chart-angular-categorical-source'/>

<snippet id='chart-angular-country'/>

All that is left is to declare the template of the angular component in which we:

- Declare a {% typedoc_link classes:RadCartesianChart %}
- Declare the {% typedoc_link classes:CategoricalAxis %} and {% typedoc_link classes:LinearAxis %} between the {% typedoc_link classes:RadCartesianChart %} open and close tags
- After that set the **`cartesianHorizontalAxis`** and **`cartesianVerticalAxis`** directive to the axes
- Finally declare a {% typedoc_link classes:BarSeries %} instance to it, bind the {% typedoc_link classes:BarSeries,member:items%} to the source of data and set the **`cartesianSeries`** directive

<snippet id='chart-angular-bar-series-component'/>
<snippet id='chart-angular-bar-series'/>

The following images demonstrate how your 'page' looks like on iOS and Android:

![Chart series overview](../../../img/ns_ui/bar_series_android.png "Bar series on Android.") ![Chart series overview](../../../img/ns_ui/bar_series_ios.png "Bar series on iOS.")

### Stack mode
There are scenarios in which a single Categorical chart can host multiple series. The {% typedoc_link classes:CategoricalSeries,member:stackMode%} property allows you to define how these series will interact with each other. The following options are available for the `stackMode` property:

- {% typedoc_link enums:ChartSeriesStackMode,member:None%} - series are displayed on top of each other in the order they are added in the chart
- {% typedoc_link enums:ChartSeriesStackMode,member:Stack%} - separate data points which reside in the same category are stacked on top of each other in the order they are added in the chart
- {% typedoc_link enums:ChartSeriesStackMode,member:Stack100%} - separate data points which reside in the same category are stacked on top of each other and positioned proportionally so that the whole plot-area of the chart is filled

This is the data with which we will populate our series:

#### Example
Just like with all angular 'pages' let's start with the `Component` in which we will place our {% typedoc_link classes:RadCartesianChart %} instance. We create a basic angular `Component` that contains a collection of objects provided by an custom service, which will be used by the chart to provide intuitive data visualization.

The service is a simple 'mock' of an backend call that will return an array of objects:

<snippet id='chart-angular-data-service'/>

Inside that service we have a single function which returns an array:

<snippet id='chart-angular-categorical-source'/>

<snippet id='chart-angular-country'/>

All that is left is to declare the template of the angular component in which we:

- Declare a {% typedoc_link classes:RadCartesianChart %}
- Declare the {% typedoc_link classes:CategoricalAxis %} and {% typedoc_link classes:LinearAxis %} between the {% typedoc_link classes:RadCartesianChart %} open and close tags
- After that set the **`tkCartesianHorizontalAxis`** and **`tkCartesianVerticalAxis`** directive to the axes
- Declare a {% typedoc_link classes:AreaSeries %} instance to it, bind the {% typedoc_link classes:AreaSeries,member:items%} to the source of data and set the **`tkCartesianSeries`** directive

<snippet id='chart-angular-area-series-component'/>
<snippet id='chart-angular-area-series'/>

The final result is shown in the two images (android and ios) below.

![Cartesian chart: Area series](../../../img/ns_ui/area_series_android.png "Area series on Android.") ![Cartesian chart: Area series](../../../img/ns_ui/area_series_ios.png "Area series on iOS.")

## Pie series
Pie series are a separate type of series that are used in context with a {% typedoc_link classes:RadPieChart %}. There are two types of Pie series supported by Chart for NativeScript:

- {% typedoc_link classes:PieSeries %} - data is represented in the form of a pie where separate data-points are **visualized as a slice** of the pie
- {% typedoc_link classes:DonutSeries %} - the Pie series principles apply here with the only difference that there is a 'hole' in the middle of the pie which makes it look like a donut
