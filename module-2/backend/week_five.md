### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

### Week 5 Questions
1. How do we make flash messages display on a page?
* create a value in the flash hash during a controller action I.E ```ruby 
def show
  ...some code...
  flash[:error] = "somethind went wrong"
  redirect_to some_path
end
```
Then add a flash div to the page you're trying to disaply the page on

2. Where is cart information/temporary information usually stored?
* in the session

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
* Making that many database calls could be stressful to our system. having that information persist though could allow users to have a persistent cart accross multiple visits to the site

4. What is the purpose of the asset pipeline?
* To control and optimize the flow of neccesary assets in http interactions

5. Why do we precompile our assets?
* So that they won't have to be sent over multiple requests and responses to and from the client

6. What do each of the following tags do?

```ruby 
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```
* the first links the stylesheet 'application' to the current erb file
* the second includes the javascript script 'application' into the current erb file
* the third links to an image file called 'rails.png'

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
* How to actaully run the code.
* What is this code for
* Where is this code in the development process
* Project Logo

8. What are the top four accessibility issues that we as developers should be aware of?

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
* callback
* in our validation methods

10. Given the following object, how would we create a scope for all users who are active?

```ruby 
User.create(name: "Happy", active: true)
```

* scope :active, where(active: true)

11. What is the difference between a scope and a class method?
* a scope will alwasy return a relation whereas a class method containing the same code would not.

### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  * cart['48'] = 4
  12b. How would you increase the quantity of item 29?  
  * cart['29'] += somenumber
  12c. How would you find out how many items your user is 
  thinking about purchasing?
  * session[:cart].count
  
13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?
* duck typing is the acceptance of objects based solely on what they are able to do. whereas polymorphism uses the overriding of methods by subclasses.

14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  
* string.gsub(/[\s(]/,"").gsub(/[)-]/,".")


### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources
-> * I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources 

Choose One:
-> * I feel confident about the content presented this week
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
