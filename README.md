mns
===

My News Scraper - Scrape news sites at demand for news articles

# Example of usage

```javascript
// require the library
var mns = require( 'mns' );

// initialize the scraper with the options for the website
// you want to get news from.
// example for Hacker News
var scraper = mns({
  url : "http://news.ycombinator.com/news",
  type : "text/html",
  // a CSS selector that gathers every article you want to scrape
  listSelector : "td:not([align]).title",
  // a CSS selector for each property you want to gather from
  // the article listing (relative to the listSelector)
  articleSelector : {
  	// you can pass an object with keys
  	// selector and attr. In this case, it specifies that
  	// you want to gather the href attribute from the "a"
  	// selector
    url : {
      selector : "a",
      attr : "href"
    },
    // or simply a CSS selector that's relative to the
    // listSelector which you specified before
    src : "span",
    title : "a"
  }
});
```

# Disclaimer

This is still a work in progress, under active development. If you have any question, feel free to open an issue on this repository.
