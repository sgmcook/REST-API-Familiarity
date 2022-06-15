# REST-API-Familiarity

HTTP requests typically have 3 parts: 
1) A verb/action
2) Metadata about the verb
3) Content related specifically to the verb

REQUESTS
=============================================
VERBS:
+ GET: Request a resource from the server
+ POST: Create a resource on the server
+ PUT: Update an already existing resource
+ PATCH: Partial update of an object
+ DELETE: Remove resource
+ more...

Typically verbs are gatekept by your access

HEADERS: 
Name/Value pairs <br>
Type of content (json, binary, etc.,)
Content length so the server has an idea
Auth: who's making the call
Accept: when you send me a response, what can I accept
cookie: passenger data

CONTENT: 
HTML, JSON, etc.
Content is verb specific 
Information to help fulfil the verb (e.g. you won't send content if you're asking a GET request because you want something)

RESPONSE
=============================================
STATUS CODE: 
What on a very basic level happened with your request on its return

HEADERS: 
Type of data, what it is, size, how long you should keep hold of it

CONTENT: 
HTML, BLOBS, text, etc. 


USING THIS IN PRACTICE
=============================================
The key thing to know is that unlike connections you're used to, the connections of a HTTP connection are only maintained
as long as the request takes to either complete, or time out. It's not maintained the whole time. 

About passing messages


REST
=============================================
Leans on the benefits of rest
Representational State Transfer

Transfer of data or state representational of the kinds of messages you want to use
- Separation of client and server
- Server requests are stateless (they don't persist outside of the message/response)
- Cacheable
- URI interface

API RULES
=============================================
Once you make an API and have people using it, you're stuck with it
You don't want to sink into adding adhoc requirements 
Understand your requirements
APIs should mature in beneficial ways for everyone

API PARTS
=============================================
URI - path on webserver
VERB - action on that URI
Headers - 
Request body

Status 
Headers
Response body

URIs are just paths to resources
Query strings are added to the end of URIs /optional
Formatting, sorting, searching
Nouns are your endpoints, and the API can action those nouns

Resources
Collection of nouns (users, payments, etc.)
Are they just entities? 
People are a type of resource, but there are nested objects (e.g. payments have IDs, etc. etc. )
JSON is pretty good at conceptialising this

Identifiers
+ each URI should point to a specific resource
+ Do not need primary keys but they do need unique identifiers
+ YOU WANT TO GET AWAY FROM PRIMARY KEYS
+ URIs are read by people so you want to structure your values in such a way that people can read them

Query strings
+ Non-resource properties, e.g. names, pages, formats
+ how the resource is returned basically

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

