# Todo_List: Independent Rails project for CS121

Contributors: 
Ashley Schmit

Summary:
Todo_List is a simple but effective app that allows you to create and add tasks to your todo list. Users register for the app with an email and password, and all of their todo list tasks are associated with their account. Once users are done with a task, they can delete it. Users also have the ability to edit tasks.

MVP:
The essential features include a registration and login so that each user will have their own todo list. Users need to be able create tasks, view a list of all the tasks they currently have, and delete tasks once they are done with them. They also need to be able to logout. 

Functionality:
Users begin on a "welcome" page where the comment tells them to create a task. The only two links avialable to them, however, are login and register. If a user has not yet created an account, they can register with an email and password. If they do have an account, the user can login, and they now have access to the following links: logout, new task, my tasks, and register. When they click on the new task link, the user can fill out the title and notes for the task, then submit the task. When they click on the my tasks link, the tasks are listed, and next to each one are the links edit, delete, and show. The show link directs them to a page with only that task on it. 

Architecture:
I have two models: Users and Tasks. A User can have many tasks, while every task can only have one User. So, it is a one to many relationship. The User has a username and password that helps differentiate between accounts. Each task has a title and a notes section as its attributes. The tasks for a given user will not be displayed unless that person is logged in. I used a rails form as the data collection interface for the user to enter the title and notes for each task. I used a gem called devise to handle the user information stuff. The registration and validation for the user accounts were handled by devise. For database storage, I used sqlite.

Issues:
One issue was that the My Tasks and New Task pages was appearing even after a user had logged out. To fix this, I moved those links in application.html.erb to within the "if current_user" statement. This seemed to fix the problem, but I think that the following bug remains. 
Bug: I think that even if you aren't logged in, if you manually enter in the url to the "my tasks" page, it will display all the tasks.

References:
“Guides.rubyonrails.org.” Getting Started with Rails - Ruby on Rails Guides, guides.rubyonrails.org/getting_started.html.
“Make an Instagram like Site in under 30 Minutes! (Ruby on Rails).” YouTube, YouTube, 6 Sept. 2015, www.youtube.com/watch?v=MpFO4Zr0EPE.
