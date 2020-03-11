# javascript-snippet

here is simple method for get Query String From URL as an object

```

function queryFromURL(){
   var search = location.search.substring(1);
      return JSON.parse('{"' + search.replace(/&/g, '","').replace(/=/g, '":"') + '"}',
          function (key, value) {
              return key === "" ? value : decodeURIComponent(value)
          })
  }
 }
```


above example will get the query strings from URL and returns as an object

i.e 

assume URL: 

`http://xyz/submit.htm?email=someone@example.com&version=v01 `

and if we call function queryFromURL() then it would return as key value paired value (object)
from above URL  ``email=someone@example.com&version=v01 ``

this will be replaced ? = to : and & will be replaced to ,and fonally when we are passing this to 
JSON.parse function it would be returned Java script object
