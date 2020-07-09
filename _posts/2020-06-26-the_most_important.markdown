---
layout: post
title:      " The Most Important "
date:       2020-06-26 17:37:09 -0400
permalink:  the_most_important
---


What’s the most important thing you should know about my program?

This was the first time in this Flatirons course that I felt I was pushed to the limit. The CLI project gave me a rollercoaster of emotions from being anxious to joyous to being stressed all in the same week. Starting out, this project had to be built from the group up. No spec.rb to guide you or no learn environment to hold your hand through the labs. This was totally YOU. I didn’t see it coming and when I did it hurt. I spent nearly a week trying to figure out if I should scrape my date which would require me to use css selectors to key out what information I wanted, or use an API that had everything in a readable manner. If I were to use an API I would need to find one first that has all the pertinent information that I need. This was cumbersome. After a week of being indecisive I found an API that would work for my program. Ah, finally a breath of fresh air it seemed.

 

With the source out of the way, I was able to iterate over each of my categories and extract out the information I needed.  Using an attr_accessor and itiailizing my categories in my states class, I was able to create my instance variables and use them in my CLI class. This was a little difficult for me at first to understand and apply in my standalone code. I think I didn’t fully understand the concept going through it when it was introduced but practicing it in my CLI really helped.

 

Once everything was defined and there were no loose ends between my classes, I moved on with developing my CLI class. To me, this felt like the brains of it all. Without this class, my API class and state class are just mere information stored somewhere. The CLI class brings this to life. The first thing on my agenda for my CLI class was to pull all the information into this CLI class. Without data, this CLI class is useless as well.  One thing I learned about coding is to have a plan of attack. I created a method that defined how my CLI will run. It kept things organized coding wise and visually. Anyone that looks at my code can see what goes where and what will be coming next. I wanted to start with a ‘welcoming’ method that would invite and introduce the user into the app. This was the easy part. Next was listing out the states for the user to choose from. After some syntax errors and undefined method errors I was able to populate a list for the user to choose from. This felt like another place where I can breathe a breath of fresh air and do a git add . / git commit –m “good progress” / git push and sit for awhile. The meat of the CLI project came where the user actually inputs information and what my app was able to retrieve from the API and return. This was challenging as I ran into a lot of errors and spent a lot of time debugging to figure out what was going on. Also, it kept on kicking my user out of the app after the first input. I was able to solve this by looping it and using a case, while, break syntax to get the app to prompt the user again.

 

Now back to the question “what is the most important thing that should know about my app?” I think the answer is simple. The most important thing to someone that just runs it in their terminal is that although it looks so simple on the outside, it is so complex in the inside. To a person that is just beginning and learning how to code, a simple CLI where it asks the user a question and to respond with an input and spits back out an input from the app is very complicated. The idea of defeat and “I will never be a programmer” ran across my mind so many times while trying to code. Now whenever I look at any app, I admire it more for what it is. I know how much work is put into creating apps now and all the long hours coding. I do have hope for the future as I start to understand more about coding, the syntax, and structure. With this understanding, I plan to be able to code more efficiently and be able to code in a DRY manner.

-----------------------------------------------------------
# .self
My first encounter with .self in my CLI is with my API Manager. Self in ruby gives me access to the object that is being called upon. In my project, self.get_states is being used to get the information from my API. It is defined as a class method and is thus an object of the class, APIManager. My second encounter in my project with self is when I took the empty array and pushed each individual object into the class variable @@all. To sum things up, self depends on where it was defined. If it was inside an instance method, self is an instance of that class. If self was defined on a class level method then self is equal to the class itself. 
