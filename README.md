# Week 3 Assessment

## Setup
* Fork and Clone this repository
* Run `update-database` - let the instructors know if you run into any issues!

## Exercise (10 Points)
### Securing the Application (4 points)
* Use Secrets Managemnt to remove the database connection string from the application.
* So that we can see the full implmentation, include a screenshot below to show your `secrets.json` file

![secrets file](https://github.com/abukhmirov/Mod4Week3_Assessment/assets/130601068/65135092-f928-4a5a-8552-2873e145b218)


### Maintaining Current-User (6 points)

This application includes some starter code so that we could maintain a current user.  Review the Login and Logout code in the Home Controller, along with the Login and Logout buttons in the Home/Index.cshtml file.  Building on this pre-existing structure:
* Create a cookie that holds a key for "currentUser" when a user logs in.
* Delete that cookie when a user logs out.
* Add the value of "current user" to all views

## Questions (10 Points)

For the following questions, answer as if you are in an interview!
1. Describe one strategy you have used to maintain state in a web application. (2 points)
I have used cookies to maintain the data of the current logged in user over the time of the session. The data is stored in the cookie and is set by the user's login form.
2. How would you protect sensitive data that we need to store in our database - for example, passwords? (2 points)
I would stored the in a Hashed/Digested form in the database to lower the risk of the passwords being stolen
3. Describe 3 additional common security risks in web development. (make sure you discuss what you know about the risk, and if you know how to minimize the risk) (6 points)
   There is SQL injection, where a malicious user might input SQL code into a form and access data in the database they shouldn't have access to. This can be prevented by filtering and sanitizing the user inputs to get rid of malicious SQL. 
There is also DDOS attacks, where the application is flooded by traffic, usually by bots. This can be prevented by API rate limiting. The amount of requests a user can make is limited in a specified time frame.
Lastly, there is Overposting, where more data is sent in than is asked in a form. The excess data could change values in the application and gain admin permissions. The Data Trasfer Object model can help with that by being inbetween the layers of the application, usually the Service layer and the UI. It only takes in the specified data and does not let in the extra data that might be sent in.

