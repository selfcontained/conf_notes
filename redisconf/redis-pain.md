# Redis Pain

---

Matt Ranney - **Voxxer**

Use Redis as a Riak Cache

+	rapidly changing data
+	data they can afford to lose

## What is Redis for?

+	sometimes it's not clear what you should use Redis for
+	what are the tradeoffs for using Redis?


## Writing to Disk Drives

+	taking snapshots is slow
+	if you have rapidly changing data, can run out of memory fast while saving
	+	Redis is recommended for rapidly changing data :P

## Reading from Disk Drives

+	can take minutes to load large database

## Avoid Pain by Expecting Less

+	Redis is a good in-memory database
+	Not going to be good to read/write data from/to disk

## Single CPU

+	only uses a single cpu/process
+	that's why we get the neat data structures though

## Fantasy World (psuedo fantasy)

	Riak / Reddis

+	Single Database....fault tolerant...

## Scaling

+	Redis cluster - in the works forever

## Operations

+	doesn't crash often
+	hard to tell what's going on
	+	it's using CPU, Memory, but why?
	