## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
* Active Record is an ORM. It allows you to easily take objects and associate them with a part of a database. It also then allows you to access that data and manipulate or relate it.

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
* .all, .first, .last, .(any other column name in the associated table). class Team inherits from Base in the active record module, which provides Team with the base active record methods.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
* Team.find(4).name
* Owner.find(Team.find(4))

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
* Team.find(4).owner

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
* Many to Many
* saved on http://ondras.zarovi.cz/sql/demo/ under 'Zachary Thomas cfu week 2'

6. Define foreign key, primary key, and schema.
* primary key is the id by which a table's rows are referenced
* foreign key references a primary key on a different table
* a schema determines the names and object types of columns in tables, as well as which table will be present in the database.

7. Describe the relationship between a foreign key on one table and a primary key on another table.
* a foreign key in one table references a related primary key on another table.

8. What are the parts of an HTTP response?
* status code
* header
* body


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
* .find finds the row with the corresponding id in the appropriate table.
* .(linked foreign table name) gives access to the corresponding table through a foreign key.
* .first returns the data in the first row in a table

2. Name your three favorite ActiveRecord rake tasks and describe what they do.
* rake db:migrate runs any migrations which are timestamped after the schema timestamp
* rake db:seed seeds the database using the seed file
* rake db:create creates database 
* honorable mention 'rake db:{drop,create,migrate,seed}' cause it's always there for you 

3. What two columns does `t.timestamps null: false` create in our database?
* created_at
* updated_at

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
* many to many

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
* create a join table holding the foreign keys for both students and teachers, see above for schema diagram

6. Give an example of when you might want to store information besides ids on a join table.
* If each instance of that relationship has some other bit of data, like a time an event happened, or in the case of teachers and students, maybe the class which they share

7. Describe and diagram the relationship between patients and doctors.
* doctors have many patients
* in the patient table, there might be a foreign key referencing a doctor

8. Describe and diagram the relationship between museums and original_paintings.
* a Museum has many original paintings
* in the painting table, there might be a foreign key that references the museum it hangs in

9. What could you see in your code that would make you think you might want to create a partial?
* If i see the exact same erb or html in multiple files, a partial could help to dry up that code.

### Self Assessment:
Choose One:
-> * I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources 

Choose One:
* I feel confident about the content presented this week
-> * I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
