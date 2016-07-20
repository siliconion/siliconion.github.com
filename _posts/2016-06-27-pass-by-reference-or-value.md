---
layout: post
title:  "Pass By Reference and Pass By Value"
date:   2016-06-27 16:48:56 -0500
categories: C# java javascript
---

**What's "pass by reference" and "pass by value"?**

This is about how parameters are sent into functions.

* "by value" means passing a copy of parameters, so the original cannot be changed.
* "by reference" means passing the parameters themselves.


**How would pass by reference or value affect my code?**

For pass by reference, the change made to the parameters will still be there outside of the function.

For pass by value, the change made to the parameters themselves will *NOT* be there outside of the function.

Note that it's the parameter *itself* that can't be changed. The things the parameter referencing to can change.


**Examples!**

All the languages I know are default to pass by value. C++, C# and PHP offers call by refernce. Here is an example in C#:

First, create a class person:
{% highlight C# %}
public class person
{
    public string name;
        
    public person(string name)
    {
        this.name = name;
    }
}
{% endhighlight %}

Then I have 3 different kinds of functions:
{% highlight C# %}
static void changeKey(person p, string name)
{
    p.name = name;
}

static void changeObj(person p, string name)
{
    p = new person(name);
}

static void changeObjByRef(ref person p, string name)
{
    p = new person(name);
}
{% endhighlight %}

Then I can get the following:
{% highlight C# %}
person bob = new person("Bob");		//Bob is Bob

changeObj(bob, "Lily");			// Bob is still Bob

changeKey(bob, "Mary");			// Bob changes name to Mary 

changeObjByRef(ref bob, "Pual");		// Bob becomes Pual            

{% endhighlight %}

Note that the `ref` keyword is required if reference is passed.


**My take**

Unless there's some particular key word to pass a reference, everything is pass-by-value. And while values don't cahnge, stuffs that being pointed to can.
This is really not that hard of a concept if you know a little bit C: val is the value, and &val is the pointer. Or, ptr cannot change, but *ptr can.

I can see how people are confused in Java and Javascript, especially using "reference" to mean multiple things, and make up terms like "Call by sharing". But do a but of comparison to C or C# and you can see the behavior is all the same.

**Reference**

* [Java is Pass-by-Value, Dammit!](http://javadude.com/articles/passbyvalue.htm)

* [In the strictest sense, C is pass-by-value](http://denniskubes.com/2012/08/20/is-c-pass-by-value-or-reference/): I think it's a bit philosophical: should we say val and &val is the same? Because if we say it's different, is there ever anything that's pass-by-reference?