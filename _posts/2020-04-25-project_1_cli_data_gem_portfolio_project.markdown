---
layout: post
title:      "Project #1: CLI data gem portfolio project."
date:       2020-04-26 00:39:32 +0000
permalink:  project_1_cli_data_gem_portfolio_project
---


I remember on the first day of orientation writing down all the milestones we would hit along the way to our journey as Software Engineering students. After the getting through the "First Mile", I knew that the next milestone coming up was the CLI data gem portfolio project. Working through those labs and lessons after the first mile and alongside being on paternity leave due to this global pandemic, I guess the days were just passing me by. Up until the first day of project week I didn't realize that the time had come. I felt both nervous and excited about working on my first project, which pretty much sums up how I have been feeling throughout the program so far.

After reading the requirements, attending study groups/OOH and watching several videos, I felt I had a decent plan as to what I wanted to do and thought I knew how to go about doing it. I'm not sure if it was my nerves or just doubting myself, but a few days went by where I kept doing the same thing and did not actually work on the project itself. After finally talking with an ed coach about how I felt and working up a schedule with my wife so that I wouldn't have to start studying later in the night, I was able to take the first few steps towards creating my project.

So now the decision came to whether or not I wanted to use an API or scrape a website for data. From what I have read and seen in several videos, APIs are generally easier to use because they are databases with data readily available for you to use. After checking out RapidAPI, I decided I came about the cocktail API and felt it was something I would enjoy working on. After watching videos and a lot of googling, I found myself struggling with how to implement the actual API and use it to grab data. After about two days of working on my cocktail CLI, I decided to try my hand at scraping because I didn't want to fall behind and it was already half way through the first project week.

After reading up more on scraping and watching videos, I found myself working a lot faster through the project. I ended up deciding to create a CLI which scraped a website that provided some brief history on Air Jordans. I used the ScraperChecker REPL and was able to pinpoint the data I wanted to use for my CLI.  I quickly put down my boilerplate code for my sneaker class which would instantiate new instances of sneaker objects and hold an array of those instances. After scraping the data from the website,  I needed to find a way to implement it into my scraper class. I initially had my results being put out as a hash, however it was not displaying the data how I wanted. 

I ended up switching up my scraper class to how it is currently:

```
 def self.scrape_jordan_info
        url = "https://pudding.cool/2018/09/jordans/"
        doc = Nokogiri::HTML(open(url))
        results = doc.css("div.details-text")
        results.each do |sneaker|
            name = sneaker.css("p.jordanName").text
            release_date = sneaker.css("span.date").text
            og_price = sneaker.css("span.price").text
            designer = sneaker.css("span.designer").text
            description = sneaker.css("p.jordanInfo").text
            JordanHistory::Sneaker.new(name, release_date, og_price, designer, description)
        end
```

So instead of the results returning as a hash with key value pairs, I was able to instantiate a new sneaker object with attributes from the data provided. Finding the correct css selectors was a fun experience and the css diner game that my cohort lead suggested definitely helped a lot. Now came the CLI class and I initially had trouble displaying the data from my scraper class. After realizing I was overthinking things, I realized that it was simple iterating over the array of sneaker objects.

This project was definitely a stressful one, mainly because I did not have much coding experience prior to bootcamp and both this program and project challenged my usual way of studying and implementing things learned. My normal way of reading and writing things down was not working out and practice definitely was the key to success. Although this was a simple application, I am definitely proud of what I accomplished. Now to study and pass the assessment!!



