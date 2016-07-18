# Google Combo Chart

This widget impelements the Google Combo Chart widget in your Mendix application! 

## Contributing

For more information on contributing to this repository visit [Contributing to a GitHub repository](https://world.mendix.com/display/howto50/Contributing+to+a+GitHub+repository)!

## Typical usage scenario

Show a column chart with an average line chart combined

## Description

A chart that lets you render two series as a different marker type from the following list: line, area, bars, candlesticks, and stepped area.

## Configuration & Properties

The widget needs an entity as it's context. It also needs a String attribute that provides JSON to populate the data table. For more information on configuration options see [The Google Combo documentation](https://developers.google.com/chart/interactive/docs/gallery/combochart). Be sure to implement the following configuration settings as well to prevent errors.

Create the following structure in your domain model. It may be non persistant. Be sure to create the StringValue entity BEFORE you create the IntegerValue. Otherwise the sorting does not work and thus the widget will not render.

![domainmodelcombo](https://cloud.githubusercontent.com/assets/10046210/16875079/b50bbc26-4a9d-11e6-9159-c5da44bbd067.png)

On the Data tab select the attribute that returns a JSON string with data. Select your prefered chart types and on the other tabs you can specify desired styling settings.

This widget needs the RestServices Module for its JSONSerializer and therefore also needs the CommunityCommons Module.

## Known issues and bugs

You have to create the StringValue entity before the IntegerValue in your domain model, because the JSONSerializer uses the internal object ID for sorting. Apparently the order in which you create your entities has influence on the object ID it receives by Mendix.