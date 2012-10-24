# SPDY

---

Roberto Peon & Will Chan

+	HTTP/1.1 since 1996
+	Pages are much larger now

## Goals

+	faster, more secure, less effort from devs

## What it does

+	compresses headers
+	prioritization

## Send ALL THE REQUESTS!

+	remove browser heuristics about prioritization
+	interleave requests, let protocol deal with ordering

## Server Push

+	better inlining
+	push the most important assets first