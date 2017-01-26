# Lets Mongoose

**Within your squads explore these questions**

What is an ODM?
- Object Document Mapper
- An ODM is a tool that maps the structure of the databases in objects. This way you can work in your documents from the database with objects, with all the great advantages that it carries.
- An ODM also abstracts usual operations with the documents, and provides with utilities that can simplify a lot common tasks.
- An ODM also has a disadvantage: the performance. This is due to using objects and abstracting operations.


What is MongooseJS?
- reference: https://github.com/Automattic/mongoose
- Mongoose is a MongoDB object modeling tool designed to work in an asynchronous environment.
- MongoDB abstraction middleware for Node. 
- Mongoose provides a straight-forward, schema-based solution to model your application data. It helps translate database data into JavaScript objects for use in an application
- It includes built-in type casting, validation, query building, business logic hooks and more, out of the box.


Why do we need MongooseJS?
- Even though MongoDB is schemaless by design, the purpose of this is to allow users to create their own schema, else data in a mongoDB database would be stored like unrelated chunks of information scattered around. 
- Using a ODM like MongooseJS allows you to define a schema which can evolve with changes in requirement and also an abstracted form of communication between Node and MongoDB


What does the word "abstraction" mean?
- [PLEASE ADD/CHANGE IF SOMETHING MAKES MORE SENSE]
- Abstraction seeks to reduce objects and methods into only relevant data that is easy to understand. 
- Abstraction makes the underlying object easier to read and call methods on by giving these methods name and making them easier for a human to understand in context.


How do we use mongoose?
- reference: http://mongoosejs.com/docs/
- Install the package and require in your node.JS
- Then familiarize yourself with the syntax.


What are models in Mongoose?
- reference: http://mongoosejs.com/docs/models.html
- Models are fancy constructors compiled from our Schema definitions.
- Instances of the models represent documents which can be saved and retrieved from our database.
- All document creation and retrieval from the database is handled by these models.


Define what schema means in Mongoose?
- reference: http://mongoosejs.com/docs/guide.html
- Everything in Mongoose starts with a Schema. Each schema maps to a MongoDB collection and defines the shape of the documents within that collection.
- Schemas not only define the structure of your document and casting of properties, they also define document instance methods, static Model methods, compound indexes and document lifecycle hooks called middleware.


How do we connect to our database?
- reference: http://mongoosejs.com/
- mongoose.connect('mongodb://localhost/test');


What is a "model"?
- a model defines a programming interface for interacting with the database(read, insert, update)
- it determines the logical structure of the database and determines the manner in which data can be stored, organized and changed
- MongoDB uses a document-oriented or document store model


What is data denormalization and data deduplication?
- in relational databases, it is an approach to speeding up read performance (data retrieval) in which
  the administrator selectively adds back specific instances of redundant data AFTER
  the data structure has been normalized. Not to be confused with a databased that has not
  yet been normalized.
- data deduplication is a specialized data compression technique for eliminating
    duplicate copies of repeating data.
- often called intelligent compression or single-instance storage.

What is "built-in-typecasting" in Mongoose?
- Typecasting is changing data from one type to another, for example an integer to a float
[POSSIBLE EXAMPLE OF MONGOOSE TYPECASTING]:
passing id as a int value and it is coerced into a string when querying the db collection??


What is the "population" feature in Mongoose?
- reference: https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/mongoose#Working_with_related_documents_—_population
- Population in Mongoose allows you to reference documents in different collections since there is no join feature.
- The process this entitles is attaching the _id to a reference and using that to pull in information from another document.



What does "virtual" do in Mongoose?
- reference: http://mongoosejs.com/docs/guide.html
- Virtuals are document properties that you can get and set but that do not get persisted to MongoDB.
- The getters are useful for formatting or combining fields, while setters are useful for de-composing a single value into multiple values for storage.
- a Virtual seems to look similar to an object's method in JavaScript


- Example Virtual : 
- // define a schema
- var personSchema = new Schema({
- name: {
  first: String,
    last: String
  }
});

// compile our model
var Person = mongoose.model('Person', personSchema);

// create a document
var axl = new Person({
  name: { first: 'Axl', last: 'Rose' }
});


- personSchema.virtual('fullName').get(function () {
-   return this.name.first + ' ' + this.name.last;
- });


Explain built-in-promises in Mongoose?
- reference: http://mongoosejs.com/docs/promises.html
- Mongoose async operations, like .save() and queries, return Promise/A+ conformant promises
- This means that you can do things like MyModel.findOne({}).then() and yield MyModel.findOne({}).exec() (if you're using co).


How are documents mapped in Mongoose?
- mongoooooooooose documents are mapped one-to-one
- Each document has their own model(based on their individual schemas)


What are custom instance methods and static methods?
- static methods are defined on the Model.
- instance methods are defined on the document.


What are the 8 built-in types that we can specify for our properties in Mongoose?
- http://mongoosejs.com/docs/schematypes.html
String
Number
Date
Buffer
Boolean
Mixed
Objectid
Array


**Review this code snippet from Mongoose's homepage**

```
var mongoose = require('mongoose');
mongoose.connect('mongodb://localhost/test');

var Cat = mongoose.model('Cat', { name: String });

var kitty = new Cat({ name: 'Zildjian' });
kitty.save(function (err) {
  if (err) {
    console.log(err);
  } else {
    console.log('meow');
  }
});

```

**Resources**
[Google Search Engine is your best friend](https://www.google.com/)
[Mongoose Official Doc](http://mongoosejs.com/)

