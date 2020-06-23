---
layout: post
title:      "Project #2: Sinatra Portfolio Project."
date:       2020-06-23 04:30:34 +0000
permalink:  project_2_sinatra_portfolio_project
---


So before I dive into the technical aspects that I have struggled with during this project, there a few things that have made this project process interesting to say the least.  I have been on my paternity leave for the past 3 months, which has made this coding journey a little easier for me because I have been able to focus more on coding daily without being exhausted from work. That changed last week when my paternity leave ended and I returned to work. I work as an inpatient Physical Therapist Assistant at a hospital in NJ and this first week back has been exhausting both physically and mentally, especially with this global pandemic. My daily coding has been squeezed into a shorter amount of time and I found myself struggling to write simple lines of code because of how tired I am from work. After many cups of coffee, energy drinks and late nights/early mornings, I can say I have gotten through creating another project. Now it may not be as pretty as I would have liked, but I can fix that up in the near future. Ok, now that I got that off my chest, lets talk code.

As with the first project, I took to YouTube to see what previous/current Flatiron students have made to get an idea of what I was getting into. After reading the project requirements, I decided to choose something I felt passionate about just like with my first project. I chose to create a web app, called "Gearhead Community", that would allow a user to showcase their cars and the parts they have added to those cars. I decided to use the Corneal gem, which helped create the main filetree needed for the entire project. I was able to quickly create my models, migrations and views without much trouble. 

The first thing that I struggled with was Associations. I understood the basic concept of `has_many` and `belongs_to` and knew that my Car Model would have `'has_many :parts` and my Part Model would have `belongs_to :car`, but I wasn't too sure on the User Model and if it would just have only `has _many :cars` or also have `has many :parts, through: :cars`. I ended up adding the latter and also created a join table called car_part to have the foreign keys of both the Car model and Part model.

The second thing that I struggled with was implementing the create/edit functionality. At first I was struggling with a user creating/editing empty form fields, however I ended up using an ActiveRecord validation to ensure that each form field was present and also not an empty string.

The third thing that I struggled with was showing the user errors. I was able to redirect or render the correct erb page if the login/signup/edit did not work properly, however the user did not get a message stating what went wrong. I was finally able to get it to work on the signup page with this bit of code:

```
<% if @u && @u.errors.any? %>
    <% @u.errors.full_messages.each do |m| %>
        <p style="color: red;">*<%= m %>!*</p>
    <% end %>   
<% end %>
```

The last thing I struggled with was CSS, mainly because at first I had changed the blue background to black through main.css, however I noticed that it wasn't changing even when I had saved the file. I remember closing out VSCode and restarting it only for it to not change. I remember coming back the next day and seeing that my background had changed colors. So I tried changing the background to an image I found online, but that wasn't showing up also. Sure enough, after about a day or so, the black background is now the background image I chose. I definitely need to go through the CSS bonus lessons sometime soon hopefully.

Overall it is awesome to see a project that involves both front-end and back-end programming. Making this project come to life had definitely given me the motivation to continue pushing through this journey, no matter how tired I am. I don't mind sacrificing some sleep now to achieve my dreams in the future! Now to pass this assessment!!


