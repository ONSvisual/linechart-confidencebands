# linechart-confidencebands
Making line charts with confidence bands.

Copy a folder for each chart you want to make.

Data is loaded from migration.csv, it has columns that look like this

|date|Series1|Series1a|Series1b|Series1c|Visas|
|----|-------|--------|--------|--------|-----|
|    |       |        |        |        |     |

In the config you specify which lines to have the bands in `dataSeriesNames`. It will look for columns with the series name and "a", "b" and "c" after to draw the three bands. "a" is the largest and has no blur. "b" and "c" both have blur.

You specify the lines use `lineSeriesNames` in the config. The colours for these lines are set with `lineColourPalette`. These lines won't have confidence bands.

Data downloads buttons correspond to data.csv, data.xls and image.png.