## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?
* A cookie is a packet of inforamtion which a browser can hold, which a server  can use to find out things like who the user is, or when they last visited the site.

2. What’s the difference between a session and a cookie?
* sessions are collections of data which the browser has access to, and last as long as the browser is open. Cookies are sent back and forth everytime, whereas sessions are just referenced in every intereaction using a session id.

3. What’s a flash and when do you want to use flashes?
* A flash is a message which can be used to indicate various things to the user, i.e 'username or password are invalid'

4. Why do people say “HTTP is stateless”?
* HTTP is stateless because it doesn't have any ability to retain information about previous http requests (it has no state of being)

5. What’s authentication? Explain.
* Authentication is the process of determining who a user is, either through referencing an existing set of credentials, or creating a new set of credentials(things like username, password, email)

6. What’s the difference between authentication and authorization?
* authorization, on the otherhand, is the determination of what users are allowed to do, i.e a visitor can view sucha dn such page, whereas an admin can edit content on that same page.

7. What’s a before filter?
* A before filter is any filtering method which is set to run before some other action.

8. How do we keep track of a user once they’ve logged in?
* usually by storing their user id in the session hash

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
* namespacing a resource is useful if you want to access some type of resource, but within the context of some concept, i.e 'admin/categories/4' would mean that we're visiting categories within the context of being an admin. Nesting resources is more generally used when all of one type of resource are goping to exist in relation to another type of resource. i.e 'vending_machine/:id/candies'.

10. At a high level, what tools can you use to implement authorization? How would you use them?
* Authorization can be implemented using enums at the model level, and then guard statements at the controller and view level, specifically before filters.

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
* Enums are associations between a numerical value, and a string, allowing that integer to stand in for that string. It allows one to easily store the role of a user.

12. What are some strategies you can use to keep your views DRY?
* guard statements can be used that check for different conditions within the view so that the same view can show different content to different kinds of users. Enumerables and other loops can also be used to creat lists of objects without repition.


### Reviews Questions 
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}
]
```  
given.sort_by{|hash| hash[:holiday][:name]}

14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300? 
(assuming the " on both indicates that both are strings)
given.delete!('$').to_i


### Self Assessment:
Choose One:
-> * I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources 

Choose One:
-> * I feel confident about the content presented this week
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
