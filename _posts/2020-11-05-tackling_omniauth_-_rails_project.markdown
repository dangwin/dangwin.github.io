---
layout: post
title:      "Tackling OmniAuth - Rails Project"
date:       2020-11-05 17:36:16 +0000
permalink:  tackling_omniauth_-_rails_project
---


I was tasked with creating a rails project that had RESTful routes. Among other requirements that it needed,
one of them were to log-in a user with OmniAuth, a multi-provider authentication that verify your credentials 
with a third party and re-routeS you back to my application if log-in was a success. I knew going into this
project that this would be a daunting task because I did not feel confident with the labs. 

It did prove to be a challenge because from the minute I created myself as a developer in Google to the time
I got it to work. My first pitfall was when I had to get the client ID and setting it up in the Google 
environment. While it seemed straight-forward at first, it was very tricky as it required me to do things
in a specific order. After looking at some Youtubes and guides, I was able to get the credentials I needed
to set-up my code. 

Since I did not use Devise for authentication, the steps for setting up OmniAuth from other guides were 
a little different. Most of the guides used Devise hand in hand with OmniAuth for all their authentication
needs. Something like that would be my next goal for my rails project since it will create all my routes 
for me. 

The hardest task for me was to link `omniauth-google-oauth2`  with my code. I didn't understand at first 
why we will needed an .env file until I knew it was something we did not want to push to Github for security purposes. 
The next thing that stumped me was when I had to try to fetch data from Google after authentication. 

```
    def self.create_from_omniauth(auth)
      User.find_or_create_by(uid: auth['uid'], provider: auth['provider']) do |u|
          u.email = auth['info']['email']
          u.password = SecureRandom.hex(16)
      end

```

Initially this was my code to generate all the info for my Users. However when running my views, their information were not being passed through (i.e. first_name, last_name). Without and first_name and a last_name, an added game or a reviewed game will not know who it belongs to. After some time, I realized I did not pass through those two parameters. 
My new code 

```
    def self.create_from_omniauth(auth)
      User.find_or_create_by(uid: auth['uid'], provider: auth['provider']) do |u|
          u.email = auth['info']['email']
          u.first_name = auth['info']['first_name']
          u.last_name = auth['info']['last_name']
          u.password = SecureRandom.hex(16)
      end

```

worked  and created users if they weren't in the database already with an appropriate first and last name linked from Google. The thing I learned from this was that I should always go back to the source of where it was created. There I will find what I did wrong. Persistent is key!

