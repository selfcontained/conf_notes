# Realtime at Disqus

---

Adam Hitchcock


## Why do realtime?

+	get data to user asap - ship your product to your customer


## How did they do it?

+	redis queue
+	python processing
+	ngingx backend - push stream module

+	[thoonk][] = queue on top of redis
	+	job queue - reliable
+	they over-publish because it's so cheap

## [ngingx push stream][]

+	[example config][]

+	Use Sentry for measuring exceptions

[thoonk]: http://blog.thoonk.com/
[example config]: https://gist.github.com/0b3b52050254e273ff11
[nginx push stream]: http://wiki.nginx.org/HttpPushStreamModule