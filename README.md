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

HEADERS: 
Name/Value pairs
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
+ 

=============================================