---
layout: post
title:  "CLI Data Gem Project: STAY RELEVANT""
date:   2016-07-19 23:29:29 +0000
---


As a budding software developer, I've increasingly found myself losing track of the news and how to make small talk with people. I hate talking about weather, and I am fascinated by pop culture by rarely have the time to keep up with the #blacklivesmatter movement, Taylor Swift's descent, or even advancement in augmented reality (why is everyone now hanging out in Prospect Park at odd hours of the night, furtively pretending like they're not training their Pokemon?). 

Do you struggle with this? Do you find yourself not being able to keep up with the kids?  

FEAR NOT -- I have the Data Gem for you! In this project, my program spits out the hottest trend from Twitter, BBC, Mashable, Huffington Post, and Gawker. I wanted to also include Google News, Fox News, and Yahoo! News, but I was getting some odd errors like:

"OpenSSL::SSL::SSLError: SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/net/http.rb:923:in `connect'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/net/http.rb:923:in `block in connect'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/timeout.rb:73:in `timeout'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/net/http.rb:923:in `connect'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/net/http.rb:863:in `do_start'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/net/http.rb:852:in `start'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/open-uri.rb:318:in `open_http'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/open-uri.rb:736:in `buffer_open'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/open-uri.rb:211:in `block in open_loop'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/open-uri.rb:209:in `catch'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/open-uri.rb:209:in `open_loop'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/open-uri.rb:150:in `open_uri'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/open-uri.rb:716:in `open'
	from /Users/Danny/.rvm/rubies/ruby-2.2.3/lib/ruby/2.2.0/open-uri.rb:34:in `open'
	from /Users/Danny/Development/code/cli-data-gem-assessment-v-000/stay_relevant/lib/stay_relevant/trend.rb:69:in `scrape_yahoo'
	from (irb):1
	from bin/console:14:in `<main>'2.2.3 :002 > exit
[16:32:39] stay_relevant"


Which I couldn't really work around with Nokogiri, but let me tell you how this project works with the five trends that I chose! 

I followed Avi's amazing tutorial about which scraped data from two deals. So let me explain how the program works: 

The program starts with bin/stay_relevant command within the gem's directory.

This file loads a ruby environment, creates a new instance of CLI class and calls .call method on it.

CLI class’s .call method lists the most recent trends with list_trends method and calls on menu which asks the user various questions. List_trends calls on StayRelevant::Trend.today (which is located in trend.rb) which lists out the five trends that I mentioned above.  

Trend.rb creates a Nokogiri object from various news websites, parses the data and creates new Trend instances that are saved within the trend array. 

The trend class only contains one attribute which is .name that tells the user about the latest trend from the five news sources. 

Here is an example of what is returned when you run the program: 

1. Twitter: #TemptationIsland
2. BBC: 'The least diverse selfie ever': The US politician Paul Ryan has sparked a debate about diversity in Washington politics and "white privilege" after sharing a selfie with a group of interns. Mr Ryan, who's the Republican Speaker of the House of Representatives, shared an image on Instagram with the caption "I think this sets the record for the most number of Capitol Hill interns in a single selfie."But thousands have pointed out that the photo is dominated by white people. Journalist: Anne-Marie TomchakVideo journalist: Alvaro A. Ricciardelli
3. Mashable: Facebook may be considering taking humans out of Trending Topics
4. Huffington Post: An Alarming Number Of People Rely On Social Media For News
5. Gakwer: Facebook Announces Sweeping Changes to Trending Section

Happy coding! 
