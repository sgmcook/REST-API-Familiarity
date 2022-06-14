# REST-API-Familiarity

HTTP requests typically have 3 parts: 
1) A verb/action
2) Metadata about the verb
3) Content related specifically to the verb

=============================================
REQUESTS
=============================================
VERBS:
GET: Request a resource from the server
POST: Create a resource on the server
PUT: Update an already existing resource
PATCH: Partial update of an object
DELETE: Remove resource
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

=============================================
RESPONSE
=============================================
STATUS CODE: 
What on a very basic level happened with your request on its return

HEADERS: 
Type of data, what it is, size, how long you should keep hold of it

CONTENT: 
HTML, BLOBS, text, etc. 


