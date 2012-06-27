Ext.ux.RequestRowExpander
=========================

An ExtJs 4.1 RowExpander Plugin that makes a server request for more detailed data 

Tested on ExtJs 4.1.0 

This plugin was created since the current Ext.ux.RowExpander only expands with the information that was contained with in the table load. It is often the case where you might want to query a URL to get more details about an object.  


Usage:
```
plugins: [{
	ptype: 'requestrowexpander',
    rowBodyTpl : [
    	'<div>',
        '{title} - {description}',
        '</div>'
    ],
    url: '/serverPath/objectInfo',
    idParam: 'uuid',
    objectRoot: 'myJSONObject'
}],
```
When a row is expanded this would generate a request to '/serverPath/objectInfo?uuid=ObjectID'. 

This would expect a reply from the server in JSON:
```
{
	myJSONObject {
		title: "Some Title",
		description: "Some Description"
	}	
}
```
This JSON Object would be passed to the template to render. 
