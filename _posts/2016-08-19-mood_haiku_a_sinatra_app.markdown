---
layout: post
title:  "Mood Haiku, a Sinatra App"
date:   2016-08-19 18:25:17 +0000
---

I'm super excited to write that I have completed the Sinatra Assessment! 

The objective of this project was to create a CRUD application that wasn't too similar to the a blog app, and I decided that I would try to create a bit of spin off of this by having some added layers of complexity. 
 
I love feelings, and I love emotions, and I sometimes I have too much F in my ENFP personality type, and I need an outlet to express myself. So my app asks users to detail their mood "What's your mood right now?" And then it says: 

Write a beautiful haiku that really captures the essence of being miserable (where this was the mood that was put in by the user previously). 

So my classes are: 
User (has_many moods, and has many_haikus through moods)
Mood (belongs to user, and has_many haikus) 
Haikus (belongs_to user, belongs_to mood) 

I'm kind of proud of the fact that I check whether or not the mood has been created before for the user, and then if it has, it'll just add another haiku to the pre-existing mood. 

I was hoping that I would be able to check if the Haiku was 5-7-5 syllables, or else tell the user to fix the errors, but I can't seem to find a library in Ruby that has a .syllable_count function.  If anyone knows about this, or can suggest an easy way to make this happen, that would be great! This is definitely something that I'd love to expand and possibly make public. 

Cheers, and happy coding, y'all!
Danny
