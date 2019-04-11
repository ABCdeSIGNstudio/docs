---
title: Candlestick series
page_title: Candlestick series | Progress NativeScript UI Documentation
description: This article gives a basic introduction of Candlestick series and continues with a sample scenario of how Candlestick series are used.
slug: chart-series-candlestick-vue
tags: series, cartesian, candlestick, vue, nativescript, professional, ui
position: 2
publish: true
---

# RadChart CandleStick Series
 This series operates with a special kind of data in the form of four parameters defining the stock market - open, high, low, and close. The high and low values show the price range (the highest and lowest prices) over one unit of time. The open and close values indicate the opening and closing price of the stock for the corresponding period. Candlestick series have body, which has a different color depending on the value of open and close prices of the financial data point. The width of the candlestick body is determined by the period between 2 candlesticks and the range of the axis. You should use the {% typedoc_link classes:LinearAxis,member:majorStep%} property of {% typedoc_link classes:LinearAxis %} to change the period between 2 candlesticks. Here is how to set up Candlestick series:

## Customization

Candlestick series have body, which has a different color depending on the value of open and close prices of the financial data point. The width of the candlestick body is determined by the period between 2 candlesticks and the range of the axis. You should use the {% typedoc_link classes:LinearAxis,member:majorStep%} property of {% typedoc_link classes:LinearAxis %} to change the period between 2 candlesticks. The following example shows how to set up Candlestick series:


## Example
Just like with all vue 'pages' let's start with the `Component` in which we will place our {% typedoc_link classes:RadCartesianChart %} instance.

Before that, we would create a basic JS or TS module that contains a collection of objects, which will be used by the chart to provide intuitive data visualization.

<snippet id='chart-get-financial-data'/>

All that is left is to declare the template of the vue component in which we:

- Declare a {% typedoc_link classes:RadCartesianChart %}
- Declare the {% typedoc_link classes:DateTimeCategoricalAxis %} and {% typedoc_link classes:LinearAxis %} between the {% typedoc_link classes:RadCartesianChart %} open and close tags
- After that set the **`tkCartesianHorizontalAxis`** and **`tkCartesianVerticalAxis`** directive to the axes
- Finally declare a {% typedoc_link classes:CandlestickSeries %} instance to it, bind the {% typedoc_link classes:CandlestickSeries,member:items%} to the source of data and set the **`tkCartesianSeries`** directive

<snippet id='chart-candlestick-vue'/>

![Cartesian chart: Scatter Bubble series](../../../../../ui/img/ns_ui/candlestick_series_android.png " Scatter Bubble series on Android.") ![Cartesian chart: Scatter Bubble series](../../../../../ui/img/ns_ui/candlestick_series_ios.png "Scatter Bubble series on iOS.")
