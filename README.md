# angular-html5-storage
[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/chovy/angular-html5-storage?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

HTML5 web storage for Angular.js (ngHTML5Storage)

## Install

    bower install angular-html5-storage --save

## Usage

create your service wrapper (optional)
```javascript
app
  .factory('myStorageService', ['ngHTML5Storage', function(ngHTML5Storage){
    return {
      saveStuffInLocalStorage: function(key, value){
        return ngHTML5Storage.local(key, value);
      },
      saveStuffInSessionStorage: function(key, value){
        return ngHTML5Storage.session(key, value);
      }
    };
  }]);

//in your controller (be sure to inject your service)
myStorageService.saveStuffInLocalStorage(key, value)
  .then(function(data){
    //it is saved in local storage
  });
```        

using ngHTML5Storage directly (without a service wrapper)
```javascript
app
  .controller('MyController', ['ngHTML5Storage', function(ngHTML5Storage){
    ngHTML5Storage.session(key, value)
      .then(function(data){
        //it is saved in session storage
      });
  });
```
## Methods of ngHTML5Storage

* `.local(key, value)` - set a value by key in localStorage
* `.session(key, value)` - set a value by key in sessionStorage
* `.local(key)` - get a value by key in localStorage
* `.session(key)` - get a value by key in sessionStoragedd 
* `.remove.local(key)` - remove by key from localStorage
* `.remove.session(key)` - remove by key from sessionStorage


## Run tests

    gulp test




MIT License


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/chovy/angular-html5-storage/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

