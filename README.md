# Confidence band line chart
A line chart with confidence bands and blurring. 
![screen shot 2018-08-02 at 10 45 31](https://user-images.githubusercontent.com/2945099/43576416-34f2b43a-9641-11e8-89a9-75678a2d4aa7.png)

[Demo](https://onsvisual.github.io/linechart-confidencebands/index.html)

## Files
![screenshot-2017-9-25 bar-and-line](https://user-images.githubusercontent.com/2945099/30830690-b82cb7dc-a23c-11e7-976d-1e7ba8069f9f.png)

The files for each chart should be of the following format:

![image1](https://user-images.githubusercontent.com/2945099/30038486-1e58ac22-91bd-11e7-8356-96fd6a65c33d.png)

The config file contains all the variables which you can adjust. Data.csv contains the data for your graph. The lib folder contains javascript libraries used. You'll also need the images folder.

If you’re making several charts they can share the same “lib” file as follows

![image2](https://user-images.githubusercontent.com/2945099/30038487-1e5cae94-91bd-11e7-9081-0ddaada98876.png)
![image3](https://user-images.githubusercontent.com/2945099/30038489-1e5d9f70-91bd-11e7-8ca6-8456a303b9da.png)
![image4](https://user-images.githubusercontent.com/2945099/30038488-1e5d650a-91bd-11e7-9746-3b1acf695c96.png)

## Data files
The chart is run from migrationdata.csv. The other data.csv is for download.

The data structure is like this

| date | series1 | series1a	| series1b	| series1c	| Visas	| HESA	| series2	| series2a	| series2b | series2c | 
| ------------- | ------------- | ------------- | ------------- |------------- | ------------- | ------------- |------------- | ------------- | ------------- |
| 2000 |   |   |   |   |   |   |   |   |   |
| 2001 |   |   |   |   |   |   |   |   |   |
| 2002 |   |   |   |   |   |   |   |   |   |
| 2003 |   |   |   |   |   |   |   |   |   |

It’s important to insure the date column is named exactly “date”, with a lower case d. 

Lines are drawn from column names specified in the config. If you want the blurry fuzzy lines you'll need to have the column name with 'a','b' and 'c' in addition, representing the 95%,60%,30% confidence intervals. The confidence is relative to the data point e.g. if the data point is 43±7 for 95%, then 7 is entered in the 'a' column not 50.

Lines without confidence bands can be specified in the config, e.g. Visas, HESA

## config.json

Open the “config.json” file.  You can open this in a text editor such as Notepad++ or TextEdit or download a code editor such as Atom, Dreamweaver, Brackets or Sublime Text 2.

### essentials
These contain the main variables which the chart will need and will possibly need changing for each new chart.
```
"graphic_data_url": "migrationdata2.csv",
```
where migrationdata2.csv is the name of the data file, must be in csv form.


```"dataSeriesNames":["series1","series2"]``` specifies the series to have the confidence bands around. The series must have additional data 

Specify the date format the data uses – see the [D3 wiki about time formatting](https://github.com/mbostock/d3/wiki/Time-Formatting). 
```"dateFormat":"%b-%y```

```"blur":3,``` specifies the strength of the blur. A smaller number means sharper bands.

```"lineSeriesNames":["Visas","HESA"],``` specifies the names of the columns to draw without confidence bands. The colours of these are set with ```  "lineColourPalette":["#B8860B","#266D4A"]```.


```"colour_palette": [ "#274796" , "green", "#E73F40", "#7BCAE2" ],``` specifies the colours for each of the series drawn with confidence bands. Values can be rgb(0,0,0), Hex values or colour names. 

`"legendLabels" : ["data1longerlabeltest", "data2longerlabeltest","data3"],` specifies the text to label the lines with confidence bands

`"legendStyle":` can be `"rect"` for squares or blank which gives thin lines. 

```
"sourceText":["Source information"],
```
sets the text for the source.

`"yAxisLabel"` specifies the label for the y-axis.

`"yAxisScale":"[0,300]",` set the y-axis. 

### optional 
```
"margin_sm": [60, 50, 0, 40],
"margin_md": [60, 50, 0, 40],
"margin_lg": [60, 50, 0, 40],
```
Sets the margin for the three different view sizes

```
"aspectRatio_sm" : [16,13],
"aspectRatio_md" : [16,12],
"aspectRatio_lg" : [16,10],
```
Set the aspect ratio for the three different view sizes

`"mobileBreakpoint" : 610,` set the width where the chart switches to the smallest view

`"xAxisTextFormat_sm_md_lg" : ["%y", "%Y", "%b %y"],` specifies the number for the x-axis for the three chart sizes



