# Simplenote

---

Fred Cheng - simperium

	Sync & Operational Transforms

## Operational Transforms

+	multiple people editing the same document
+	defining operations is up to the application
	+	insert characters at a position
	+	add/subtract numbers
	+	insert/remove json property
+	Handle operations in application
	+	generate operations explicitly
	+	intercept application events
	+	implicitly derive operations from application state
		+	determine how to "migrate"/"diff" from old to new state
		+	can miss intermediate operations