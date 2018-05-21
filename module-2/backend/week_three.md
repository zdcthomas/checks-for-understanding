## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
* rails new App <args>
2. What do Models generally inherit from in rails?
* ApplicationRecord
3. What do Controllers generally inherit from in a rails project?
* ApplicationController
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
resources :horses, only:[:show]
5. What rake task is useful when looking at routes, and what information does it give you?
* rake routes
6. What is an example of a route helper? When would you use them?
* user_path, users_path, route helpers are useful when it's better to not specify the string for a path
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
* _path will return just the ending of the url(the path)
* _url will return the entire url
8. What are strong params and why are they necessary?
* strong params are the explicit filtering of keys and values in the params hash, only letting through the things we need
9. What role does `form_for` play in helping us create our forms?
* form for automates the creation and submittion of forms, taking in objects and returning params related to that object
10. How does `form_for` know where to submit the user's input?
* it takes the object that's passed in and constructs a route based on that and the file that it's in. e.g @user submits to post /users from the new user form.
11. Create a form using a `form_for` helper to create a new `Horse`. 
```
<%= form_for @horse do |f| %> %>
  <%= f.label :name %>
  <%= f.text_field :name %>

  <%= f.label :breed %>
  <%= f.text_field :breed %>

  <%= f.label :weight %>
  <%= f.number_field :weight %>

  <%= f.label :owner %>
  <%= f.text_field :owner %>

  <%= f.submit "Submit"%>
<% end %>
```

12. Why do we want to validate our models?
* validating attributes of our models makes sure that the neccesary attributes of our models are present
13. What are the steps of the DNS lookup?
* the browser sends the url to the os, the os consults a dns look up server, which returns the related IP address which the os then gives to the browser so the browser can create the appropriate http request


### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?
* horse.move(prance)
* or if the question is about definitions:
    class Horse
      def move
        prance
      end
    end
15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3? 
```ruby
 furniture[:purcharsed]
 furniture[:table][:height]
```
16. What is inheritance?
* inheritence is the transfer of behaviors from one class to a subclass, ie from parent to child

### Self Assessment:
Choose One:
-> * I was able to answer every question without relying on outside resources 
* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources 

Choose One:
->* I feel confident about the content presented this week
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
