
A - Application
P - Programming
I - Interface

A set of services or [Functions](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Tools%2FFunction) that enable two [[Software]] services to communicate with each other using definitions and specific [Protocols](obsidian://open?vault=Obsidian&file=Tech%2FNetwork%2FPROTOCOLS%2FProtocol)

Every API is based on an [[API Request]] and always gives at least an [[API Response]] to see if all went well, of course if the API return actual [[Data]] the response will be different

APIs can be [Synchronous](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FMISCELLANEOUS%2FSynchronous) or [Asynchronous](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FMISCELLANEOUS%2FAsynchronous), generally they are Asynchronous as it fits better actual use in production

Technically all those methods could be unified, however Its a [Network](obsidian://open?vault=ANOTA%C3%87%C3%95ES&file=Tech%2FNetwork%2FNetwork) interest to know whatever is happeing, how many [[POST]] [[API Request]]s are happenning and so on, aswell as the code being easier to read

responses:
- **200**: Success.
- **404**: Not Found.
- **401**: No Permission.
- **500**: Server error.

It's common to use the same [URL](obsidian://open?vault=Obsidian&file=zzzzzzzzzzz%2FURL) for an api with a different method, so /user can both select all users or insert new ones

#### Security

An api can be protected through roles, you can say an api can only be accessed by admins for example, you can assign a users role

a specific role generates a token that identifies the role

when requesting the api you can specify your role to validate the request, you basically pass it as a [Parameter](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Tools%2FParameter) like a body

