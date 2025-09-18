One good way to analyze if the application should be a monolith or a distributed system is focusing on [[Architecture characteristics]]

if you need a component that needs to be highly performant, you might not want to mix it with a component that needs to be higlhy security, so you dont have to worry about those two at once, then it makes sense to distribute the system