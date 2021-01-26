----
Execution phases:
* get message
* move to processing stack with meta information {node_id, process_time (??)} (or not??)
* delete after execution (server can possibly fail after execution)
* Profit!

-----
Redis:
* (streams)[https://redis.io/commands/xadd]
* multiple streams for tons of messages (???)
* a currently selected message to process should go somewhere to handle status and should be removed from whole queue set(???)
* preProcessed message should have enough information to be handled by another server (???)

----
Logs:
* a processed message should be pushed to log (history).

----
Servers:
* in real world servers nodes don't have own names. Possible some docker ids. Thou failed message should be taken by the new one server firstly.
* if there is now new server it should be re-queued to the "main" set(-s) on the first place.

