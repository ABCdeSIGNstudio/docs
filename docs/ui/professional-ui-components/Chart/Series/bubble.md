---
title: Bubble
page_title: Bubble series | Progress NativeScript UI Documentation
description: This article gives a basic introduction of Bubble series and continues with a sample scenario of how Bubble series are used.
slug: chart-series-bubble
tags: series, cartesian, bubble, nativescript, professional, ui
position: 8
publish: true
---

# RadChart Bubble Series
Bubble series are {% typedoc_link classes:CategoricalSeries %} and are used in the context of a {% typedoc_link classes:RadCartesianChart %}, {% typedoc_link classes:CategoricalAxis %} and {% typedoc_link classes:LinearAxis %}. On top of the requirements for a {% typedoc_link classes:CategoricalAxis %}, {% typedoc_link classes:BubbleSeries %} require an additional setup parameter which should come from the data source that defines the *bubble size*. The value for this parameter is supplied by defining the {% typedoc_link classes:BubbleSeries,member:bubbleSizeProperty%}.

## Customization
On top of the customization options that come from the {% typedoc_link classes:CategoricalSeries %} context, {% typedoc_link classes:BubbleSeries %} expose the {% typedoc_link classes:BubbleSeries,member:bubbleScale%} property which can be used to fine-tune the size of the bubbles according to specific application requirements. The way the {% typedoc_link classes:BubbleSeries,member:bubbleScale%} property works is by multiplying its value to the radius of calculated for each data-point's bubble.

## Example
The following definition represents the data context that will be used to populate the Bubble series with data:

<snippet id='bubble-data-source'/>

We use an instance of this model to assign it as the *bindingContext* of the page we have put our Bubble series on:

<snippet id='binding-context-bubble-series'/>

And finally, in the XML definition of the page we put a {% typedoc_link classes:RadCartesianChart %}, add a {% typedoc_link classes:BubbleSeries %} instance to it and bind the series to the source of data:

<snippet id='bubble-series'/>

![Cartesian chart: Bubble series](../../../img/ns_ui/bubble_series_android.png "Bubble series on Android.") ![Cartesian chart: Bubble series](../../../img/ns_ui/bubble_series_ios.png "Bubble series on iOS.")

## References
Want to see this scenario in action?
Check our SDK examples repo on GitHub. You will find this and many other practical examples with NativeScript UI.

* [Series Examples](https://github.com/NativeScript/nativescript-ui-samples/tree/master/chart/app/examples/series)

Related articles you might find useful:

* [**Area Series**]({% slug chart-series-area %})
* [**Bar Series**]({% slug chart-series-bar %})
* [**Pie Series**]({% slug chart-series-pie %})
* [**Range-Bar Series**]({% slug chart-series-range-bar %})
* [**Scatter-Bubble Series**]({% slug chart-series-scatter-bubble %})
* [**Scatter Series**]({% slug chart-series-scatter %})
* [**Spline Series**]({% slug chart-series-spline %})
* [**Line Series**]({% slug chart-series-line %})
* [**Area Series**]({% slug chart-series-spline-area %})
* [**Candlestick Series**]({% slug chart-series-candlestick %})
* [**Ohlc Series**]({% slug chart-ohlc-series %})
