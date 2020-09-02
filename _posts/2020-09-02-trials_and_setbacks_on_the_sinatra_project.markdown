---
layout: post
title:      "Trials and setbacks on the Sinatra Project"
date:       2020-09-02 13:24:05 +0000
permalink:  trials_and_setbacks_on_the_sinatra_project
---



De-bugging is a big part of any developer’s workflow and Booleans also play a huge role in it. I remember an instance I had yesterday while working on my Sinatra project. My project kept crashing after submitting an edit to a review and I was unsure why. I ran a binding.pry after my @user = current_user to see what my @user is. It returned nil in the terminal and I thought that was strange. Even though I am logged in as a user right now, my app does not see my user and there must be a disconnect somewhere. I thought to myself why @user is currently false. I quickly back tracked to where I defined my current_user method to see what could’ve gone wrong there. 
My code for my current_user method was 
@current_user =  User.find_by_id(session[:user_id] if session[:user_id]. Going through my debugging process, if I type User.all, I’m able to find all of my Users and therefore it is true or it exists. I know that wasn’t the issue. So I knew it had something to do with my session[:user_id]. I quickly looked in my application controller to see if I had actually even enabled sessions. Lo and behold, I did not. Therefore every time that I would call on current_user, it could never initiate the session because it was never enabled in the first place. Backtracking really helped me with debugging and finding the root source of the issue.


