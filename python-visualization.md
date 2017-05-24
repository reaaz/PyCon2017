# Python Visualization Tools
## Started with matplotlib
### Pros
* Designed like MatLab
* Many rendering backends (png, svg)
* Can reproduce just about any plot (with effort)
* Well-tested
### Cons
* API is verbose
* Style defaults are poor
* Poor support for web/interactive graphs
* Slow for large & complicated data
## Pandas (built on matplotlib)
 * One-liner for a scatterplot
## Seaborn (built on matplotlib)
 * pairplot
## JavaScript-based Viz
* Common-idea: build a new API that produces a plot serialization (in JSON) that can be displayed in the browser (often in Jupytr notebooks)
### Bokeh
#### Pros
* Web view/interactivity
#### Cons
* No vector output (pdf/eps)
* Newer tool wirth smaller user base
### Plotly
#### Pros
* Similar to bokeh
* Animation supports
#### Cons
* Some features require a paid plan
## Visualization for larger data
### Datashader
* Fast server-side engine for dynamic data aggregation (ex: fire map)
## Declarative Visualization
### holoviews
* Datasets themselves stored in objects that automatically produce intelligent visualizations
* Composition and interactivity via operator overloading
* Renders to bokeh, datashader, and matplotlib
* Can handle geographic data and time series
### altair
* Instead of pushing pixels, pass around visualization specs and data
* Declarative visualization - think about data and relationships rather than incidental details
### d3
 * Used by NYTimes
 * Verbose
### Vega - declarative specification for visualizations built on D3
### Vegalite - way simpler than Vega, toss in the data and the type of graph