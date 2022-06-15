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

HEADERS:<br>
Name/Value pairs<br>
Type of content (json, binary, etc.,)<br>
Content length so the server has an idea<br>
Auth: who's making the call<br>
Accept: when you send me a response, what can I accept<br>
cookie: passenger data<br>

CONTENT:<br>
HTML, JSON, etc.<br>
Content is verb specific <br>
Information to help fulfil the verb (e.g. you won't send content if you're asking a GET request because you want something)<br>

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

It's all about passing messages, not maintained connections


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
Headers - metadata about the request
Request body - value returned

Status - What happened on 
Headers - metadata about the response
Response body - value returned if 

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