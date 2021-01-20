---
layout: post
title:      "Project #4: JS Frontend/Rails Backend Portfolio Project"
date:       2021-01-20 19:32:54 +0000
permalink:  project_4_js_frontend_rails_backend_portfolio_project
---


Wow, portfolio project #4!! Seems so surreal that after this project, there is only one project left to do in the curriculum and then...graduation. Well I don't want to jump the gun because this mod was definitely difficult. From all the various JS concepts to personal blockers, this mod was easily the most difficult to go through. I am currently still working full-time as a PTA during the day. Luckily I'm not currently working on the inpatient side and don't have to worry as much with COVID (+) patients. But working full-time, wanting to spend time with family, going through this course and the fact that I'm moving in a month or so, I'm stressed out. I'm trying my best to juggle things and keep reminding myself that once I pass this mod, there's only one more mod to go! So I have to just bear down and get through it, I know it'll be worth it in the end!

So once again I tend to struggle with the CSS/Styling aspect, however I was able to squeeze in some more design aspects compared to my Rails project. With each sneaker object, I was able to create the individual cards, however I still need to work on implementing them so that they render next to each other instead of below one another. I was able to find a nice background image which also helped make the SPA pop more. I put bootstrap into index.html, because I hope to utilize it to style the SPA better in the near future.

One issue that I ran into was a `500 (Internal Server Error)`  when trying to delete a sneaker object. Turns out that the reason the sneaker wasn't delete on the page was because in the Rails backend I used a private method called `set sneaker` which created a local variable that was set to find a specific sneaker. Everything started working once I ditched the private method and created a local variable within the destroy method itself. Also I noticed that once I reloaded the page after deleting a sneaker object, the sneaker object wasn't actually deleting. It was because I used `sneaker.delete` instead of `sneaker.destroy`. Main diffrence is that destroy runs any callbacks, where as delete does not. I was able to resolve this issue by fixing my delete action in my sneakers controller. 

Another issue I was running into was with the Serializers not rendering the JSON data initially. At first, with just `render json:`, both the SneakerController and CommentController were both able to render the seeded data as JSON data without any issue. For some reason, once I added the serializers it was rendering an empty array instead of the seeded data. I was able to figure out that the issue once again was the use of instance variables rather than local variables.

This is the MVP of this SPA as of now, I do plan on adding some additional features to the app in the future. Now to record the walkthrough and study for the assessment! I honestly am still in shock of how far I've gone in this journey so far and will continue to push myself regardless of how exhausted and difficult it may be because this is something I want to pursue. I'm one step closer to my dream of breaking into the tech world and will push myself to work harder and harder each day to get there!


