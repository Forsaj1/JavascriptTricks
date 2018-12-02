# JavascriptTricks

// Parse URL Queries in WebdriverIO
```js
function url_query( query ) {
    query = query.replace(/[\[]/,"\\\[").replace(/[\]]/,"\\\]");
    var expr = "[\\?&]"+query+"=([^&#]*)";
    var regex = new RegExp( expr );
    var results = regex.exec( browser.getUrl );
    if ( results !== null ) {
        return results[1];
    } else {
        return false;
    }
}

// Example => /?Parameter=fancy
var url_param = url_query('Parameter');
if( url_param ) {
    alert(url_param); // "fancy"
}
```
