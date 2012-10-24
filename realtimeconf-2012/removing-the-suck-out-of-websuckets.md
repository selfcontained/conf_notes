# Removing the Suck out of Websuckets

---

Arnout Kazamier - Nodejitsu

## Websockets

+	Websocket Protocol release in 2009
+	December 2011 it was finalized

## Browser Support

+	latest RFC support is only the most current browsers

## Known Issues

+	AutoProxyDiscovery enabled on Safari 5.1.4 - can crash browser
+	Writing to a closed WebSocket will crash mobile safari
	+	can wrap response on messages in a setTimeout to delay invocation and let current event loop finish
		+	allows a closed property to be set correctly
+	3G doesn't always work w/ WebSocket or causes crashes
	+	sniff for mobile devices, don't use websockets there
+	ESC key in firefox will drop the established connection
	+	disable escape key if there is a current connection
+	sending invalid utf-8 can drop the connection, (emojis)
	+	unescape & encodeURI content - unescape(encodeURIComponent(emojihere))
+	Firefox doesn't connect to ws:// from a secure https page
+	Safari doesn't let you connect using self-signed certs

## Connection Blockage

+	firewalls, enterprise proxies, anti-virus blocking
	+	usually when not using port 80

## Recomendations

+	use port 443
	+	fixes a lot of the proxy and virus scanner issues
+	use an upgrade path for connection, not downgrade
+	offer multiple ports for handling anti-virus
+	Don't use websockets on Mobile

## [Real-Time Platform][http://realtimeplatform.org]

+	workarounds, like killing loading spinner on different browsers
