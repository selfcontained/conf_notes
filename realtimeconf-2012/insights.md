# Insights

---

Guillermo Rauch

	engine.io and socket.io analytics

## Server Insight

+	require('debug')('wat')
	+	DEBUG env var - such as 'http' - will output that debug scope

```
DEBUG=engine* node app.js
```

## Meta Events

+	Access to internal events
	+	socket.on('packet')

## engine.io-monitor

+	Similar to the Redis MONITOR command
	+	require('engine.io-monitor')
+	Realtime insight into latency

## Client insight
+	'debug' module works in browser
+	localStorage == process.env
	+	too much noise
+	[Chrome Extension][extension]
	+	IO Chrome Extension (in progress)
	+	visualize and log events related to socket.io/engine.io

[extension]: https://github.com/guille/insights-chrome