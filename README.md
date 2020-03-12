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




# Show JSON data with formatted in React JS#


```

import React, { Component } from 'react';
import { render } from 'react-dom';
import Hello from './Hello';
import './style.css';

class App extends Component {
  constructor() {
    super();
    this.state = {
      name: 'React'
    };
  }

  render() {
    const title="Hello";
    let obj = [
      {
      name: 'name1',
      age: 20
    },
      {
      name: 'name1',
      age: 20
    },
      {
      name: 'name1',
      age: 20
    }
    ]
    return (
      <div>
        <div><h3>{title}</h3><pre>{JSON.stringify(obj, null, 4)}</pre></div>
      </div>
    );
  }
}

render(<App />, document.getElementById('root'));


```

![output](jsontoreact.png)
