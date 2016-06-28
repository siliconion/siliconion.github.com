---
layout: post
title:  "Pass by reference and pass by value"
date:   2016-06-27 16:48:56 -0500
categories: C# java javascript
---

**What's "pass by reference" and "pass by value"?**
This is about how parameters are sent into functions.
"by value" means passing a copy of parameters.
"by reference" means passing the parameters themselves.
It's pretty obvious in C: x is pass by value, and &x is pass by reference.

**How would pass by reference or value affect my code?**
For pass by reference, the change made to the parameters will still be there outside of the function.
For pass by value, the change made to the parameters themselves will *NOT* be there outside of the function.

Note that it's the parameter *itself* that can't be changed. The things the parameter referencing to can change.
Again it's obvious in C: the pointer doesn't change, but the stuff being pointed to can change.

**Examples!**



[link](http://javadude.com/articles/passbyvalue.htm)
