# Applied Redis Search

---

Josiah Carlson

	[Redis in Action][book]

## String Searching

+	Most approaches are naive, grep/ack/locate/find, regex
	+	don't pre-process for incremental searching
+	Preprocess approaches
	+	Suffix tries / BWT preprocess

## Inverted Index

+	Preprocessing approach
	+	extract words from document to find later
+	Redis - create a SET of words => documents
	+	SET intersections on *documents*


[book]: http://www.manning.com/carlson/