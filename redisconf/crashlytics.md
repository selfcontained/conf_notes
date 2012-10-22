# Crashlytics - Modile App Crashes

---

Jeff Seibert

## Strings - Activity Tracking

+	Active user tracking - when did the user last do something
+	Bitmaps
	+	SETBIT, BITCOUNT, GETBIT
+	SETBIT "accounts:active"	4	1
	+	accounts::active::2012-10
	+	accounts::active::2012-10-01
	+	accounts::active::2012-10-01-01
+	Get active users
	+	BITCOUNT "accounts::active::2012-10-22"
		+	(integer) 3
	+	GETBIT "accounts::active::2012-10-01" 4
		+	(integer) 0/1
+	Weekly active? don't use it a lot, compute it
	+	BITOP OR "destination_key" "key1" "key2" "key3"
	+	BITCOUNT "destination_key"
	+	BITOP AND "dest" "key1" "key2"
+	Bitmask approach works for any boolean value

## Hashes - Event Tracking

+	decide how fine you want to store the data
+	multiple writes for each level of granularity, or script w/ lua

```
app:key : {
	day1: crashCount,
	day1_hour1: crashCount,
	day2: crashCount,
	day2_hour1: crashCount                                                                                                                                                            
}
```

## Sorted Sets - Leaderboards

+	map strings to ids (mongo ids) => autoincrement id
+	ZSET - scores = unique ids
+	can script this w/ lua - atomic execution