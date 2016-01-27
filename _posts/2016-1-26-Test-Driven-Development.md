---
layout: post
title: Test Driven Development
---

This week(8) we are learning about testing.

Testing! Exciting!

Our instructor warned us not to give up on testing this week even though we would quickly become incredibly bored. It is easy to see why it is the natural reaction to testing (so far). 

For weeks we have been writing code and be able to see it spit out magic! Testing is like watching an instructional video on how to stay safe while riding a bike when you have been riding a bike for weeks (and have the bumps and scrapes to prove it).

For those who do not know, tests are what you write for your code that makes sure it is working as intended. Ideally, it is written before you write your code.

For example, I am going to have a instance method in the User class that will check to see if a user has an email. First, I would write a test:

```
describe "User has a " do
	let(:user){User.new(email: "me@gmail.com")}
	it "#email? should return true if a user has an email" do
		expect(user.email?).`to eq(true)
	end
end
```

Then, go to my code and write the actual method:

```
def email?
	if email
		true
	end
end
```

This seems incredibly simple, and it is. I even asked my instructor if it is common to write more lines of testing than actual code, and he said it was!

Bizarre, I thought. But there are two amazing advantages to TDD that struck me while we were working through the exercises:

1. Tests allow you to write pseudo for all of your code. Often I think I know what I want my code to do, and how I should write it. But often I am wrong (no surprise, right?). Writing pseudo code and thinking through it first can help to avoid headaches that would come about when I just dive in and do not stop to think.

2. Tests are a safety net for everyone involved. You are working on an app and everything is humming until it is not. Tests are a great way to find what may have broke or has changed. Run the tests and see what comes up failing.

These are two advantages that I want to have more of when I am building apps, and I look forward to implementing TDD as see what other great advantages it brings.

(Ruby, Rails, RSpec, FactoryGirl)
