# Meteor & DDP

---

Matt Debergalis

## What we've learned

+	apps are moving to the client
+	massive architectural change
	+	movement of client/server to web-based apps
	+	business models are even very different
+	opportunity to define new definition for this change
	+	HTTP, REST will potentially be less important

## Data on the wire

+	JSON over the wire
+	client-side cache
	+	prefetch data so it is available
	+	invalidation logic - server pushing new data to the client
+	remote methods available for the clients
+	no standard for it

## DDP

+	wire protocol Meteor uses
+	servers publish sets of documents

```
CLIENT: {msg: "SUB", name: "newestPosts"}
SERVER: {
	msg: "DATA",
	collection: "posts",
	id: 1,
	set: {title: "First Post", author: "Matt"}
}
```

	abstract form

```
<- SUB newestPosts [asdf]

-> SET posts 1 title 'First Post'
-> SET posts 1 author 'Matt'
-> SET posts 2 title 'Followup'
-> SET posts 2 author 'Matt'

-> SET posts 8 title 'Todays news'
-> SET posts 8 author 'Sam'

-> UNSET posts 2 title
-> UNSET posts 2 author
-> SET posts 1 title 'Matthew'
```

+	Subscriptions can be parameterized

## Method Calls

```
<- CALL upvotePost 1 [asdf]
-> RES asdf 'okay'
```

+	tie subscriptions and method calls together
+	method invocation should also know about when it's data has all arrived
	+	```READY <METHOD_INVOCATION_ID>```
+	methods should only be invoked once
	+	server knows which methods have been invoked (method uuid client generated)
	+	server "replays" response to the client that it has cached

## Future APIs

+	PubSub
+	Remote method calls
+	interopability is possible once we settle on a wire protocol
+	lets keep it simple