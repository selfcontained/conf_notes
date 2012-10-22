# Ratequeue

---

Alan Shreve - **Twilio**

	fast, distributed queueing / rate limiting system

+	Phone networks have bounded rates, but developers/customers can make requests at higher rates (no rate limits)
	+	anti-spam regulations
	+	origination is a limited resource, needs to be multiplexed to all their customers
	+	leaky-bucket queue

## Goals

+	Efficient
+	Generic
+	Transactional
	+	requeue items that are not completed
+	Pull-based queue
+	Customizable
	+	change rate limits, queue sizes on the fly
...

