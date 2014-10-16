revel-mgo
======

mgo module for revel framework

## Module Use

### app.conf

Settings can be configured via the following directives in app.conf.

#### modules.rmgo
  
module.rmgo=github.com/creativelikeadog/revel-mgo

Please review the documentation at [Revel - Modules - Overview](http://revel.github.io/manual/modules.html) for more information

#### rmgo.host

Please review the documentation at [mgo.Session.Dial()](http://godoc.org/labix.org/v2/mgo#Dial) for information on the syntax and valid settings.

#### rmgo.method

This can be one of 'clone', 'copy', 'new'. See [mgo.Session.New()](http://godoc.org/labix.org/v2/mgo#Session.New) for more information.


#### rmgo.database

The name of the default database you want to use

### Embedding the controller

In any controller you want to have mongo connectivity you must include the
MongoController.

Add the following import line in source files that will embed MongoController.

     "github.com/creativelikeadog/revel-mgo/app"

Embed the MongoController on your custom controller;

    type Application struct {
  		*revel.Controller
      		rmgo.MongoController
  		// Other fields
  	}


Your controller will now have a MongoSession variable of type *mgo.Session and a Database variable of type *mgo.Database. Use this
to query your mongo datastore.

### Running sample

revel run github.com/creativelikeadog/revel-mgo/sample
