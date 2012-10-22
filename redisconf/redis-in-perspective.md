# Redis in Perspective

---

Salvatore Sanfilippo

+	DSL for Abstract data types - data structures in memory
+	Maintain focus on current featureset instead of growing featureset
	+	project becomes too large to manage, less useful for consumers, not as good at specific focus
+	Memory - serving data from memory is the focus
	+	memory continues to grow on hardware, and get cheaper
	+	2 attempts to move redis storage to disk, but that ends up being what other systems already provide
	+	ensure what is in memory is replicated to disk instead
+	Data structures & API - not really any layers between keys in memory, and how to access them
	+	even w/ lua scripts, it conforms to the available redis API
+	Very lean code w/in Redis
+	Fight against complexity - simplicity is very important in the future of Redis
+	Two distinct APIs - not everything requires a scalable solution
	+	distributed (cluster) & centralized
+	Optimize for joy - simple to get started, keep it enjoyable for users
	+	good documentation - writing doc is a great way to discover difficiencies in your system
