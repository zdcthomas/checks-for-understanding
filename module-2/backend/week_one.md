## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
* Get
* Post
* Put
* Delete
* Patch

2. What is Sinatra?
* Sinatra is a Ruby Gem which provides methods for connections through ports, transfering data between a view model and a controller.

4. What is MVC?
* Model, View, Control, is an architecture which can describe the structure of a server.

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
* conventions in path naming makes code more readable and can provide distinctions between multiple paths which would otherwise be the same

6. What types of variables are accessible in our view templates without explicitly passing them?
* 

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    erb :index
  end
  ```

  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

```ruby
  get '/horses' do
    :locals => {:name => "Mr. Ed"}
    @count = 1
    erb :index
  end
  ```

9. What's the purpose of ERB?
* ERB allows ruby code to run in, and be returned as, html

10. Why do I need a development AND test database?
* It's often neccesary to populate a test database with small amounts of data points, and then quickly remove them to make room for the next test. A development database is instead meant to hold a larger dataset to simulate how a production database might

11. What is CRUD and why is it important?
* Create, Read, Update, Delete, are the primary actions a controller might be able to use on a model.

12. What does HTTP stand for? 
* Hyper Text Transfer Protocol

13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these 
two ways?
* <% ...Some Ruby Code ... %> will run the ruby code, but will not represent the return of that ruby code in html.
* <%= ...Some Ruby Code ... %> will run the ruby code and will also represent the return of that ruby code in html

14. What's an ORM?
* Object Relational Map, it relates objects in code to data within a table

15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
* Active Record

16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD 
functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
* Get '/restaurants' allows for Reading the entire set of restaurants
* Get '/restaurants/:id' Reads and individual restaurant
* Get '/restaurants/:id/edit' Displays the screen which allows the user to edit data about a certain restaurant
* Post '/restaurants/:id' Updates the a certain restaurants data
* Delete '/restaurants/:id' deletes a certain restaurant from the db
* Get '/restaurants/new' displays page for creating a new restaurant
* Put '/restaurants' Creates a new restaurant

17. What's a migration? 
* A migration is a way to change or create a database or tables within that database

18. When you create a migration, does it automatically modify your database?
* No, the migration has to be run after it is created to modify the database

19. How does a model relate to a database?
* An ORM relates a model to a database by relating the objects that a model creates to data in the database

20. What is the difference between `#new` and `#create`?
* new creates a new instance of a class
* create creates a new instance of a class and enters it into the database/table it is associated with

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film? 
* 
```ruby
require 'films.csv'
require 'CSV'
CSV.for_each('./data/films.csv', headers: true, header_converters: :symbol) do |film|
  Film.create(id:          film[:id],
              title:       film[:title],
              description: film[:description]
              )
  end
end
```


22. Given the following hash:
```ruby
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores'] 
}
```
How would I add 'granola bar' to things you should have when hiking?
* activities[hiking][supplies] << 'granola bar'

23. What are the 4 Principles of OOP? Give a one sentence explanation of each.
* Encapsulation - Objects should only have access to the data which the absolutely need to have, and onjects should only allow access to data which need to be reached

* Abstraction - Behaviors and data types are able to be abstracted out of any particular instance, so that they can be used in different situations

* Inheritence - Object types can inheret behaviors from classes

* PolyMorphism - inherited methods can be used on many different data types


### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few <- I don't remember explicitly encountering the 4 principles of oop before, but I knew the terms which comprise it.

* I was able to answer a few questions independently, but relied heavily on outside resources 

Choose One:
* I feel confident about the content presented this week <- 
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
