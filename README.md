unserialize
===========

jQuery unserialize plugin



Overview:
========


This plugin contains two functions that works in the opposite way of 
jQuery's "serialize()" function. 

That is, where "serialize" takes a form (or a collection of inputs) and 
returns an proper serialized string for HTTP requests, the functions in
this plugin takes that serialized string and then do one of two possible
things:

1) Setting the value of every input (including selects, textareas, and 
checkboxes) in a form according to the values in the string.

2) Returns a JSON object with the values stated on the string.



How to use:
==========

This plugin has two use cases. First, it does exactly the opposite as 
"serialize()".

Let's say we have a form with id "testform", and it has two text inputs,
named "testvar1" (with a value of "1") and "testvar2" (with value "a").
If you proccess it with "serialize", this way:

```JavaScript
var result = $("#testform").serialize();
```

You should obtain the string "testvar1=1&testvar2=a".
So, the first use case for unserialize, assuming we have another form 
with id "testform2" and the same fields ("testvar1" and "testvar2"), is 
this:

```JavaScript
$("#testform2").unserialize(result);
```

What happens then is that the second form get all the values stated in 
its inputs.



The second use case is similar, but not directed to de-serializing the 
string into a form but into a JSON object. That's useful for scripting 
using the form's values. 

```JavaScript
var obj = $.unserialize(result);
```

Now "obj" is the JSON object "{testvar1:1, testvar2:'a'}".

Note how this time we don't use a selector, as this use case does not 
requires one. We call unserialize right from the jQuery namespace (or 
"$"), and NOT from a selector operation result ("$(stuff)"). 


TODO:
=====

* Unserialize from JSON objects to forms or collection of inputs.





