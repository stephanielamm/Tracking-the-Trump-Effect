# Tracking-the-Trump-Effect

> An application to see how the stock market responds to Donald Trump's tweets about companies. A responsive Vue.js single page application.

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

### Components
> App.vue
> Parent: about.vue
> stockData.vue, tweetData.Vue, dropDown.vue, analysis.vue and Intro.vue call back to About.vue

#### Static Elements
> JSON:
> twitter-data.json

> Photos:
> Donald Trump Twitter Bio Pic: dt.jpg
> Yahoo Finance Graphs for each company are named according to '(TickerSymbol).png'

##### Installation Notes
> This project uses Bootstrap and jQuery. I have included the files in this package, but if you encounter trouble make sure they are installed correctly. 

###### Screencaps

> Here is the working header and drop-down menu.
> The drop-down menu should call up data on the company from twitter-data.json.

<img src="demo-header.png">

> Here is how the company information, twitter information and analysis should appear. In mobile each div expands to full-width.

<img src="demo-tweet.png">

> After trying to implement HighCharts, HighStocks, D3 and GoogleCharts, I settled on screenshots of Yahoo Finance data in order to meet my submission deadline. I will continue to work with data and various visualization tools after this project is graded, with the final goal being to create a component that calls company-specific stock data from a json file.

<img src="demo-stock.png">
