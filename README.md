# linechart-confidencebands
Making line charts with confidence bands.

Data is loaded from migration2.csv, it has columns that look like this

|date|Series1|Series1a|Series1b|Series1c|Visas|
|----|-------|--------|--------|--------|-----|
|    |       |        |        |        |     |

In the config you specify which lines to have the bands in `dataSeriesNames`. It will look for columns with the series name and "a", "b" and "c" after to draw the three bands. "a" is the largest and has no blur. "b" and "c" both have blur.

You specify the lines use `lineSeriesNames` in the config.
