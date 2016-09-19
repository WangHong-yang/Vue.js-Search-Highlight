# Vue.js-Search-Highlight

## Introduction
Vue.js tutorial gives Grid Component Example (Search Component) [here](https://vuejs.org/examples/grid-component.html). To make users easier to find matched search key, I added highlight function to it. 

See highlight effect here:
[Vue.js Search Highlight - my blog](http://mr-why.com/post/category/frontend/vuejs-search-highlight)

## Code
1. [Edit and See outcome in JSFiddle](https://jsfiddle.net/HubertWang/t5ac1quc/)
2. [Github Code Page](https://github.com/WangHong-yang/Vue.js-Search-Highlight)

## Details
It is pretty easy to make search highlight with only 10 lines of codes!

The idea of achieving this is to add a **filter** to match the search key in the table. 

```js
Vue.filter('highlight', function(words, query){
    var iQuery = new RegExp(query, "ig");
    return words.toString().replace(iQuery, function(matchedTxt,a,b){
        return ('<span class=\'highlight\'>' + matchedTxt + '</span>');
    });
});
```

In the JS code, `RegExp` function is to make case insensitive. Then the next line of code uses JS original function `replace` to add a `<span>` tag with highlight CSS to matched letters.

In the HTML, apply the **filter** we write to the [content], matching by the [filterKey]. 

```html
{{{[content] | highlight [filterKey]}}}
```

The final step: add highlight style in CSS file.

```css
.highlight {
    background-color: yellow;
}
```

Highlight done with *exactly* ten lines of codes! Enjoy your achievement :)

(With any question, contact me anytime by leaving a comment [here](http://mr-why.com/post/category/frontend/vuejs-search-highlight). I will reply ASAP. -- Hubert Wang)
