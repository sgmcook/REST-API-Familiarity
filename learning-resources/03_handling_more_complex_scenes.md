Designing associations
=============================================
Clearly, there are going to be some associations between objects
e.g. I could have: 
+ api/customes/123/Invoices
+ api/games/halo-3/ratings
+ api/invoices/2003-01-24/payments

Which has little ambiguitity. In the first bullet point, I'm clearly not going to return all invoices, but rather only those of customer 123

Associations should return the same shapes as one another, e.g.:
+ api/customers/123/Invoices
+ api/invoices 

won't return the same values, but their lists should be the same "shape"

There are no limits on the number of associations that an object can have to it.

Searches should use queries, not associations to find resources

As much as you can for the users, assciations are the easiest way of seeing groupings of resources, but obv you don't want to go crazy nesting

Paging
=============================================
Unless you list of resources is super concrete (countries on earth, us states, etc.) you'll likely want to page
Query strings are probably better than URI sections
You probably want to tell the users how many pages they can expect

Error codes
=============================================
You could just return status codes, but it's not ideal for non-devs
How are you going to communicate your errors? 

e.g. error 400 Bad Request, but also {error: "Failed to supply X"}
If it needs to be secure, you probs don't want to give too much info though e.g. username

Caching
=============================================
Basic tenet of rest
Server side can cache, but it's not super restful

Basically, let's say I make a request but nothing has changed since the last time I tried to get it
I can pass the version I'm looking for, and if the version hasn't changed since then I respond with
304 not modified to point that out. That way my server doesn't have to go and get the actual info

Basically using headers/metadata to determine whether or not an operation even needs to happen
Strong caching = this value will be valid for a good long time
Weak caching = this value is only valid for a short time

We return eTags in our response to that any requests can provide it back 

Functional APIs
=============================================
+ pragmatic
+ Does an actual function/operational
+ Not actually restful
+ Can bake them into the API but you HAVE TO document them
+ Not an excuse to build an RPC layer

You want to ensure that you're not exposing commands that you only want your devs to use

Async APIs
=============================================
+ Some APIs aren't restful