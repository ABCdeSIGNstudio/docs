---
title: Labels styling
page_title: Labels Styling | Progress NativeScript UI Documentation
description: This article explains how the visual appearance of Telerik Chart's labels for NativeScript can be customized.
slug: chart-labels-styling-angular
tags: chart, labels, styling, angular, nativescript, professional, ui
position: 2
publish: true
---

# Styling Chart Point Labels
In order to show series default labels you should set the {% typedoc_link classes:ChartSeries,member:showLabels %} property of each series to true. By default its value is false. If you want to style the point labels that are shown for series values you can initialize the {% typedoc_link classes:ChartSeries,member:labelStyle %} property of the series with instance of {% typedoc_link classes:PointLabelStyle %}.
Supported properties are: 
- {% typedoc_link classes:PointLabelStyle,member:fillColor %}: the point label background fill color 
- {% typedoc_link classes:PointLabelStyle,member:strokeColor %}: the color of the label stroke
- {% typedoc_link classes:PointLabelStyle,member:margin %}: the margin of label
- {% typedoc_link classes:PointLabelStyle,member:textFormat %}: the string used as a formating string for label value. This format must comply to [IEEE printf Specification](http://pubs.opengroup.org/onlinepubs/009695399/functions/printf.html)
- {% typedoc_link classes:PointLabelStyle,member:textColor %}: the label font color
- {% typedoc_link classes:PointLabelStyle,member:textSize %}: the size of label font 
- {% typedoc_link classes:PointLabelStyle,member:fontName %}: the font name. If it is missing from the OS the default font is used instead.
- {% typedoc_link classes:PointLabelStyle,member:fontStyle %}: specify the style of font. {% typedoc_link enums:ChartFontStyle,member:Bold%}, {% typedoc_link enums:ChartFontStyle,member:Italic%}, {% typedoc_link enums:ChartFontStyle,member:BoldItalic%} and {% typedoc_link enums:ChartFontStyle,member:Normal%} values can be used. Defaults to {% typedoc_link enums:ChartFontStyle,member:Normal%}.

#### Example

To better illustrate styling of point label let's look at the following example:

- Declare the {% typedoc_link classes:LineSeries %} instances, bind their {% typedoc_link classes:AreaSeries,member:items%} to the source of data and set the **`tkCartesianSeries`** directive
- In order to customize the `labelStyle` open and close an **`PointLabelStyle`** tag between the **`LineSeries`** tags and set the **`tkLineLabelStyle`** directive on it

<snippet id='chart-angular-labels-styling'/>

This is how the chart looks like now:

iOS:

![Axis styling](../../../img/ns_ui/labels_styling_ios.png "iOS")

Android:

![Axis styling](../../../img/ns_ui/labels_styling_android.png "Android")

### Axes Labels

All axes have their default labels. They are visible by default. In order to display or hide them, you simply need to use the **showLabels** property of the axis. If you want to learn more about styling axis labels please visit [Axis Styling] ({% slug axis-styling %} "Learn more about styling axes")
