Object mapping plugin for [Knockout](http://knockoutjs.com/) - Find the documentation [here](http://knockoutjs.com/documentation/plugins-mapping.html).

Fork is for investigating and proposing changes re object properties not being exposed as observables.

Repo

```javascript
var pojo = {
    "myProperty": "Some value",
    "myObjectProperty": {
      "childProperty": "Some child value",
    }
  },
  viewModel = ko.mapping.fromJS(pojo),
  myProperty = ko.isObservable(viewModel.myProperty) ? "is" : "is NOT?!?!",
  childProperty = ko.isObservable(viewModel.myObjectProperty.childProperty) ? "is" : "is NOT?!?!",
  myObjectProperty = ko.isObservable(viewModel.myObjectProperty) ? "is" : "is NOT?!?!";
  
document.getElementById("first").textContent = "myProperty " + myProperty + " an observable property";
document.getElementById("second").textContent = "myObjectProperty.childProperty " + childProperty + " an observable property";
document.getElementById("third").textContent = "myObjectProperty " + myObjectProperty + " an observable property";

// results
//myProperty is an observable property 
//myObjectProperty.childProperty is an observable property 
//myObjectProperty is NOT?!?! an observable property 
```

[Related fiddle](https://jsfiddle.net/zo372vcp/)


  
