# Observability

---

Daniel Shaw - *voxer*

	observabilty is hard, especially at scale

## Priorities for realtime apps

+	scalability
	+	we build realtime stuff so it can scale (become social, etc.)
+	observability
	+	we keep it all sane

## Observer tools

+	logging
+	health/status endpoints
+	REPL
+	log aggregation
+	monitoring
+	metrics
+	DTrace

## Logging

	logging is your friend

+	don't be afraid of logging
+	disabling logging is severely limiting and a premature optimization
+	you can go too far
	+	expensive to serialize objects
	+	noise reduces observability

## Health/Status Endpoints

+	process.memory
+	process.uptime
+	process.versions
+	process.pid
+	connections
+	proc: cpu microtime (smartos only)

## REPL

+	netcat/socat
+	replify on npm
+	repl-client

## Log Aggregation

+	loggly, graylog2, splunk, winston/winstond, files + grep

## Monitoring

+	boundary, nagios, reconnoiter, circonus, Munin

## Metrics

+	statsd
+	something new from voxer soon...
	+	@sentientwaffle
	+	[llquantize][]

## DTrace

---

observability means optimizing software for humans

[llquantize]: https://github.com/sentientwaffle/llquantize