#Typeahead.js Component for Leaflet Maps

This component embeds a search bar on top of leaflet maps, with functionalities provided by Twitter's typeahead.js

## Installing

Use Bower to install the leaflet-typeahead package.

```sh
bower install --save leaflet-typeahead
```

Include the appropriate javascript dependencies in your html file.

```html
<link rel="stylesheet" type="text/css" href="bower_components/leaflet-typeahead/leaflet-typeahead.css">
<script src="bower_components/leaflet-typeahead/leaflet-typeahead.js"></script>
```

##Usage
Please refer to the typeahead [docs](https://github.com/twitter/typeahead.js/blob/master/doc/jquery_typeahead.md) for more details.

`L.control.typeahead(options, [*datasets], [typeahead custom event object])`

###typeahead custom event object
A javascript object, with keys denoting custom event names and values corresponding to respective event functions.

The special key `placeholder` denotes the display placeholder text in the search bar.

##Demo
```javascript
L.control.typeahead({
  hint: true,
  highlight: true,
  minLength: 1
},{
  name: 'val',
  source: function(val, syncResults, asyncResults){
    //lookup source here
  },
  display: 'formattedVal',
  templates: {
    suggestion: Handlebars.compile('<div>{{formattedVal}}</div>')
  }
}, {
    placeholder: 'Search',
    'typeahead:select' : function(ev, suggestion) {
      //custom action here
    }
}).addTo(map);
```
