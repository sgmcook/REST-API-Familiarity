VERBS
=============================================
Not every verb should work with every resource

IDEMPOTENCY
=============================================
The idea that an operation can be executed multiple times without changing the result
e.g. each verb should always do the same thing resulting in an effect, e.g.
    GET, PUT, PATCH, and DELETE always do the same thing even if you do it repeatedly
POST is not idempotent because the result of posting to an API will always result in a brand new object

E.g. if you're trying to put (update an already existing object) the same thing over and over again, your api should just return with the same result each time.
If it doesn't and it returns something like a bad request and message "No Changes Detected", then it's failing idemopotency

GENERIC THINGS
=============================================
+ You don't want to just map the data store (e.g. sql, csv) to the returned API call because often data useful in one data store mightn't be useful in another format
+ Don't expose unecessary server side details
+ You want to design your api in a method that's understandable for your likely clientelle
+ Given the prevelence of JSON, it's probably wise to use that but if you do, make sure you're using casing that JScript devs will be using
+ Be consistent across your endpoints
+ Think about paging data as you don't want to flood requestors with all the data
+ Think about what properties you DON'T want to include

HYPERMEDIA & REST
=============================================
+ Allows results to be self-describing
+ Allows programmatic navigation

E.G. returning collection but you can also have a set of links (_links) which describe our objects so that software can navigate to them more easily