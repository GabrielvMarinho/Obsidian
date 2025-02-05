
A - Application
P - Programming
I - Interface

A set of services or [[Function]]s that enable two [[Software]] services to communicate with each other using definitions and specific [[Protocol]]s

Every API is based on an [[API Request]] and always gives at least an [[API Response]] to see if all went well, of course if the API return actual [[Data]] the response will be different

APIs can be [[Synchronous]] or [[Asynchronous]], generally they are Asynchronous as it fits better actual use in production

Check the [[Method]]s for API interactions:
1. [[GET]]
2. [[POST]]
3. [[PUT]] or [[PATCH]]
4. [[DELETE]]
Technically all those methods could be unified, however Its a [[Network]] interest to know whatever is happeing, how many [[POST]] [[API Request]]s are happenning and so on, aswell as the code being easier to read

responses:
- **200**: Success.
- **404**: Not Found.
- **401**: No Permission.
- **500**: Server error.

It's common to use the same [[URL]] for an api with a different method, so /user can both select all users or insert new ones

#### Security

An api can be protected through roles, you can say an api can only be accessed by admins for example, you can assign a users role

a specific role generates a token that identifies the role

when requesting the api you can specify your role to validate the request, you basically pass it as a [[Parameter]] like a body

