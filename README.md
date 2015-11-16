rss-pipes
=========

RSS feed aggregator by Node.js

About
-----

This is yet another feed aggregator primary for JavaScript users.
Filters are written in JavaScript and modifiable through web browsers.

Access
------

Please visit:

<http://rss-pipes.herokuapp.com/>

TODOs
-----

* Garbage collection of filters (that are not used for a week)
* Cache control

FILTERS
-----

An example filter (shorten descritpion and strip tags):

```javascript
function rssPipesFilterFunction(articles) {
  articles.forEach(function(article) {
    article.description = article.description.replace(/(<([^>]+)>)/ig,"");
    if (article.description.length>150)
      article.description=article.description.substr(0,150)+"...";
  });
  return articles;
}
```
