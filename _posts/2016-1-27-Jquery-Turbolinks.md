---
layout: post
title: Jquery-Turbolinks
---

I had an issue with a past rails project, [Sea Dogs](https://github.com/stevenrayesky/pirate_ships_project), where on initial page load my javascript was not working. On click, I giant message was supposed to flash on the screen to let the user know that they had successfully "stalked" a boat. Unfortunately, it only worked when the page was then reloaded.

As I understand it (and I am still figuring it out), turbolinks is a gem that is on by default in rails. From the turbolinks github:

```
Turbolinks makes following links in your web application 
faster. Instead of letting the browser recompile the 
JavaScript and CSS between each page change, it keeps the 
current page instance alive and replaces only the body 
(or parts of) and the title in the head. 
Think CGI vs persistent process.
```
Faster pages. Pretty cool, right? 

Well, in my case things got a little screwy when mixed with Jquery. Let's see if I can make sense of it:

On a page, I click to a link that has some jquery. It looks like this:

```
$(document).ready(function(){
	$(".boat_image").click(function(){
		$(this).siblings(".expedition_form_div").css("display", "inline");
	});
});
```

Looks ok, right? Only problem is with Turbolinks, the document is not "ready", because it is not fully loaded. Turbolinks is going around that and only replacing the body.

In order to fix this I required another gem that fixes this specific problem, [Jquery-Turbolinks](https://rubygems.org/gems/jquery-turbolinks).

3 easy steps to get it working:

1. Put turbolinks in the Gemfile

![Jquery-Turbolinks_Gemfile]
(../../images/Jquery_Turbolinks_Gemfile.png)

2. In your application.js file in your Javascript folder require it. Note the order, it is relevant.

![Jquery_Turbolinks_app_js]
(../../images/Jquery_Turbolinks_app_js.png)

3. Finally 
`gem install jquery-turbolinks` 
and you should be all set!
