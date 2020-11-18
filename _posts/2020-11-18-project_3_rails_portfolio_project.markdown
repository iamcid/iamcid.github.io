---
layout: post
title:      "Project #3: Rails Portfolio Project"
date:       2020-11-18 07:12:38 +0000
permalink:  project_3_rails_portfolio_project
---


Just as I did with the last two blog posts regarding portfolio projects, here's a little update on my coding journey/life. I never thought for a second that this career change would be a breeze, but man has this been a rough couple of months since the Sinatra project. I'm still working full time at the hospital and with this global pandemic going on, my daily routine has been exhausting to say the least. Many nights have been spent fighting heavy eyes at my desk trying to squeeze in a little more time for coding, only to succumb to slumber. 

I initially was part of the 030220 PT SE cohort, however after returning to work full time and roughly averaging only around 3 hours on a good night of coding. I felt I needed to repeat the Rails mod because although I believe I could have passed the project assessment, I did not feel fully prepared as I did for the past two projects and did not want to just get by without understanding Rails better. Fast forward to now and I do feel like I do have a better understanding of Rails this second time around, however that did not make this project any easier to do.

I was able to work through the parts that I struggled with the first time around and ran into problems with parts that I didn't have a problem with initially. For example I didn't have any problems with implementing google omniauth the first time I created a rails app, however this time around I could not figure out why it was giving me a problem. Come to find out it wasn't anything in the code I wrote, however it had to deal with a validation. Got rid of the validation and voila! 

```
def self.create_from_omniauth(auth)
        User.find_or_create_by(uid: auth['uid'], provider: auth['provider']) do |u|
            u.username = auth['info']['first_name']
            u.password = SecureRandom.hex(16)
        end
    end
```

This class method found in the User model is the block of code I had to keep tinkering with to get to work. Initially I had put in an "u.email =" prior to the password while following along with documentation and articles I found , however I came to realize my User doesn't have an email field and therefore didn't need it. Brain fart, man I need sleep.

Another thing that I struggle with is implementing CSS styling, well having the time to implement better CSS I should say. I am hoping to be able to continue working on styling my app prior to my project assessment and see if I can challenge myself to make a better looking app.

Definitely excited to get started with Javascript and will continue to remind myself why I decided to pursue this career change! 








